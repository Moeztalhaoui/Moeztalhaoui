package com.moez.android;

import android.app.Activity;
import android.content.Intent;
import android.graphics.Color;
import android.os.Bundle;
import android.view.Gravity;
import android.view.View;
import android.widget.Button;
import android.widget.LinearLayout;
import android.widget.TextView;

public class MainActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        // تهيئة تخطيط الشاشة
        LinearLayout layout = new LinearLayout(this);
        layout.setLayoutParams(new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.MATCH_PARENT,
                LinearLayout.LayoutParams.MATCH_PARENT));
        layout.setOrientation(LinearLayout.VERTICAL);
        layout.setBackgroundColor(Color.WHITE);
        layout.setGravity(Gravity.CENTER);

        // إضافة نص الترحيب
        TextView textView = new TextView(this);
        textView.setText("تحدي الحض");
        textView.setLayoutParams(new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.WRAP_CONTENT,
                LinearLayout.LayoutParams.WRAP_CONTENT));
        textView.setTextColor(Color.RED); // تغيير لون النص إلى اللون الأحمر
        textView.setTextSize(24); // تكبير حجم النص
        textView.setGravity(Gravity.CENTER);
        layout.addView(textView);

        // إضافة نص الوصف
        TextView descriptionTextView = new TextView(this);
        descriptionTextView.setText("أنا معز بن مصطفى بن حسين، المعروف بـ المعلم للصيانة، مبتكر لعبة [تحدي الحض]. يسعدني أن أرحب بكم في عالم هذه اللعبة التي صممتها بعناية لتكون مصدرًا للمتعة والتسلية والتحدي لكل من يلعبها.");
        descriptionTextView.setLayoutParams(new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.WRAP_CONTENT,
                LinearLayout.LayoutParams.WRAP_CONTENT));
        descriptionTextView.setTextColor(Color.GREEN); // تغيير لون النص إلى اللون الأخضر
        descriptionTextView.setTextSize(18); // تكبير حجم النص
        descriptionTextView.setGravity(Gravity.CENTER);
        descriptionTextView.setPadding(0, 20, 0, 20); // إضافة تباعد بين النص والعناصر الأخرى
        layout.addView(descriptionTextView);

        // إضافة زر بدا اللعبة
        Button startGameButton = new Button(this);
        startGameButton.setText("بدا اللعبة");
        startGameButton.setLayoutParams(new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.WRAP_CONTENT,
                LinearLayout.LayoutParams.WRAP_CONTENT));
        startGameButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // ابدأ النشاط الجديد
                startActivity(new Intent(MainActivity.this, CvActivity.class));
            }
        });
        layout.addView(startGameButton);

        // إضافة زر الخروج
        Button exitButton = new Button(this);
        exitButton.setText("خروج");
        exitButton.setLayoutParams(new LinearLayout.LayoutParams(
                LinearLayout.LayoutParams.WRAP_CONTENT,
                LinearLayout.LayoutParams.WRAP_CONTENT));
        exitButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // اخرج من التطبيق
                finish();
            }
        });
        layout.addView(exitButton);

        setContentView(layout);
    }
}
