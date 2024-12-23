
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        EditText adsoyadi1 = findViewById(R.id.adsoyadi);
        EditText yasis1 = findViewById(R.id.yasis);
        Button buttonCheck = findViewById(R.id.buttonCheck);
        TextView textyazısı = findViewById(R.id.textview1);

        buttonCheck.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View v) {
                String yasInput = adsoyadi1.getText().toString();
                String adıInput = yasis1.getText().toString().toLowerCase();

                if (yasInput.isEmpty() || adıInput.isEmpty())
                {
                    textyazısı.setText("Lütfen tüm alanları doldurun.");
                    return;
                }

                int yas = Integer.parseInt(yasInput);

                if (yas >= 18 && adıInput.equals("evet"))
                {
                    textyazısı.setText("Ehliyet alabilirsiniz.");
                } else
                {
                    textyazısı.setText("Ehliyet alamazsınız.");
                }
            }
        });
    }
}
