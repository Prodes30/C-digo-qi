import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.annotation.DrawableRes
import androidx.compose.foundation.Image
import androidx.compose.foundation.border
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.Spacer
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.padding
import androidx.compose.foundation.layout.size
import androidx.compose.foundation.layout.width
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Surface
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.layout.ContentScale
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import br.qi.noite.ui.theme.ProjetoNoiteTheme

class MainActivity : ComponentActivity() {
override fun onCreate(savedInstanceState: Bundle?) {
super.onCreate(savedInstanceState)
setContent {
ProjetoNoiteTheme {
// Aqui, vão os códigos
// que serão o App em si.
}
}
}
}

@composable
fun ProfileName(
@DrawableRes image : Int,
name : String,
time : String,
modifier : Modifier = Modifier
) {
Row(verticalAlignment = Alignment.CenterVertically) {
Image(
painter = painterResource(id = image),
contentDescription = "Foto do perfil",
contentScale = ContentScale.FillBounds,
modifier = modifier
.size(46.dp)
.clip(CircleShape)
.border(
width = 2.dp,
color = Color.Gray,
shape = CircleShape
)
)

    Spacer(
        modifier = Modifier.padding(horizontal = 6.dp)
        )

    Column {
        Text(
            text = name,
            fontSize = 22.sp,
            fontWeight = FontWeight.Bold
        )
        Text(
            text = time,
            color = Color.Gray,
            fontSize = 12.sp

        )
    }
}
}

@Preview(showBackground = true)
@composable
fun ProfileNamePreview() {
ProjetoNoiteTheme {
ProfileName(
image = R.drawable.chaves,
name = "Chaves" ,
time = "2 horas atrás"

    )
}
}
