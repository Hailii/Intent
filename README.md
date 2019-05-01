# 实验5
## Intent
### 新建一个工程用来获取 URL 地址并启动 Intent
#### 截图
#### 输入为空时会提示
![无法显示](/images/1.png)
#### 输入网址
![无法显示](/images/2.png)
#### 弹出选择框
![无法显示](/images/3.jpg)
#### 显示网页
![无法显示](/images/4.jpg)
#### 关键代码
```
    private String urlHead="https://";
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button button1=(Button)findViewById(R.id.button);
        button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                EditText edit1=(EditText)findViewById(R.id.editText);
                String url=edit1.getText().toString();
                if(url.isEmpty()){
                    edit1.setError("请输入网址");
                }
                else {
                    Intent intent = new Intent(Intent.ACTION_VIEW);
                    intent.setData(Uri.parse(urlHead+url));
                    startActivity(intent);
                }
            }
        });
    }
```

