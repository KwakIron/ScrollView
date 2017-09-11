# ScrollView
```
package com.guozhe.android.scrollview;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.ScrollView;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity implements View.OnClickListener{
    private ScrollView scrollView;
    private Button button,button2;
    private TextView textView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        initView();
    }
    private void initView(){
        button = (Button)findViewById(R.id.button);
        button2 = (Button)findViewById(R.id.button2);
        textView = (TextView)findViewById(R.id.textView);
        scrollView = (ScrollView)findViewById(R.id.scrollView);
        button.setOnClickListener(this);
        button2.setOnClickListener(this);
        StringBuilder builder = new StringBuilder();
        for(int i=0;i<100;i++){
            builder.append("데이터"+i+"\n");
        }
        textView.setText(builder);

    }

    @Override
    public void onClick(View view) {
        switch (view.getId()){
            case R.id.button:
                scrollView.fullScroll(ScrollView.FOCUS_DOWN);
                break;
            case R.id.button2:
                scrollView.fullScroll(ScrollView.FOCUS_UP);
                break;
        }
    }
}
