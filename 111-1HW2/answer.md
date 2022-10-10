# 第2次作業-作業-HW2
>
>學號：109111106
><br />
>姓名：陳宗鋕
><br />
>作業撰寫時間：180 (mins，包含程式撰寫時間)
><br />
>最後撰寫文件日期：2022/10/10
>

本份文件包含以下主題：(至少需下面兩項，若是有多者可以自行新增)
- [x]說明內容
- [x]個人認為完成作業須具備觀念

## 說明程式與內容

先列出一個陣列及另一個二維陣列並指定炸彈的位置，並將所有二維陣列顯示為0，
然後將炸彈的位置轉換為"*"字，再來判定炸彈周圍要不要+1，再進行字元轉型，最後列出陣列結果。

```csharp
protected void Page_Load(object sender, EventArgs e)
        {
            int[] ia_MIndex = new int[10] { 0, 7, 13, 28, 44, 62, 74, 75, 87, 90 };
            char[,] ca_Map = new char[10, 10];

            for (int i_Row = 0; i_Row < 10; i_Row++)
            {
                for (int i_col = 0; i_col < 10; i_col++)
                {
                    ca_Map[i_Row, i_col] = '0';
                }
            }

            
            
            for (int i_ct = 0; i_ct < 10; i_ct++)
            {
                int i_Row = ia_MIndex[i_ct] / 10;
                int i_col = ia_MIndex[i_ct] % 10;

                if ((i_Row - 1) >= 0 && (i_col - 1) >= 0)
                {
                    int i_Tmp = Convert.ToInt32(ca_Map[i_Row - 1, i_col - 1]);
                    i_Tmp++;
                    ca_Map[i_Row - 1, i_col - 1] = Convert.ToChar(i_Tmp);
                }

                if ((i_Row) >= 0 && (i_col - 1) >= 0)
                {
                    int i_Tmp = Convert.ToInt32(ca_Map[i_Row, i_col - 1]);
                    i_Tmp++;
                    ca_Map[i_Row, i_col - 1] = Convert.ToChar(i_Tmp);
                }

                if ((i_Row - 1) >= 0 && (i_col) >= 0)
                {
                    int i_Tmp = Convert.ToInt32(ca_Map[i_Row - 1, i_col]);
                    i_Tmp++;
                    ca_Map[i_Row - 1, i_col] = Convert.ToChar(i_Tmp);
                }

                if ((i_Row + 1) < 10 && (i_col + 1) < 10)
                {
                    int i_Tmp = Convert.ToInt32(ca_Map[i_Row + 1, i_col + 1]);
                    i_Tmp++;
                    ca_Map[i_Row + 1, i_col + 1] = Convert.ToChar(i_Tmp);
                }

                if ((i_Row + 1) < 10 && (i_col) >= 0)
                {
                    int i_Tmp = Convert.ToInt32(ca_Map[i_Row + 1, i_col]);
                    i_Tmp++;
                    ca_Map[i_Row + 1, i_col] = Convert.ToChar(i_Tmp);
                }

                if ((i_Row) >= 0 && (i_col + 1) < 10)
                {
                    int i_Tmp = Convert.ToInt32(ca_Map[i_Row, i_col + 1]);
                    i_Tmp++;
                    ca_Map[i_Row, i_col + 1] = Convert.ToChar(i_Tmp);
                }

                if ((i_Row + 1) >= 0 && (i_col - 1) >= 0)
                {
                    int i_Tmp = Convert.ToInt32(ca_Map[i_Row + 1, i_col - 1]);
                    i_Tmp++;
                    ca_Map[i_Row + 1, i_col - 1] = Convert.ToChar(i_Tmp);
                }

                if ((i_Row - 1) >= 0 && (i_col + 1) < 10)
                {
                    int i_Tmp = Convert.ToInt32(ca_Map[i_Row - 1, i_col + 1]);
                    i_Tmp++;
                    ca_Map[i_Row - 1, i_col + 1] = Convert.ToChar(i_Tmp);
                }
            }

            for (int i_ct = 0; i_ct < 10; i_ct++)
            {
                int i_Row = ia_MIndex[i_ct] / 10;
                int i_col = ia_MIndex[i_ct] % 10;
                ca_Map[i_Row, i_col] = '*';
            }

            for (int i_Row = 0; i_Row < 10; i_Row++)
            {
                for (int i_col = 0; i_col < 10; i_col++)
                {
                    Response.Write(ca_Map[i_Row, i_col]);
                }
                Response.Write("<br>");
            }
```


## 個人認為完成作業須具備觀念

開始寫說明，需要說明本次作業個人覺得需學會那些觀念 (需寫成文章，需最少50字，
並且文內不得有你、我、他三種文字)

這次作業沿用上一次隨堂的程式，加了一些規則，讓整體難度變高，並需要熟知if的語法與使用方法，還須了解轉換型別。


