---
output: 
  html_document:
    keep_md: true
  word_document:
    toc: yes
    reference_docx: "example.docx"
toc-title: "Оглавление"
---




```r
originals_data <- read_csv2("data/raw/some_data.csv") %>% 
  select(!ID) %>%
  mutate(across(where(is.character), as.factor))
```

```
## ℹ Using "','" as decimal and "'.'" as grouping mark. Use `read_delim()` for more control.
```

```
## Rows: 4760 Columns: 32
## ── Column specification ────────────────────────────────────────────────────────
## Delimiter: ";"
## chr  (2): V0_GRP, V0_DEM_GEN
## dbl (30): ID, V0_DEM_AGE, V1_SYMPTOMES, V2_SYMPTOMES, V1_CB_WBC, V1_CB_RBC, ...
## 
## ℹ Use `spec()` to retrieve the full column specification for this data.
## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

\newpage

# Таблица 1 — Статистическая таблица


```r
#originals_data %>%
#  rename(`Группа` = V0_GRP) %>%
#  get_combined_table("Группа", significant_digits = 2) %>%
#  base_flextable() %>%
#  merge_v(c("Переменная")) %>%
#  merge_v("Переменная", target = c("p-value", "p-value (между группам скорр., fdr)", "Значимо различающиеся группы")) %>%
#  color(i = ~ `p-value (между группам скорр., fdr)` %>% str_remove("<") %>% str_remove("\\(ANOVA\\)") %>% #str_remove("\\(Kruskal test\\)") %>% str_remove("\\(t\\)")  %>% str_remove("\\(w\\)") %>% str_replace(",", "\\.") %>% #as.numeric() %>% `>=`(0.05), color = "darkgray")
```


```r
iris %>%
  head() %>%
  base_flextable()
```

```{=html}
<div class="tabwid"><style>.cl-67440ed6{}.cl-673862e8{font-family:'Arial';font-size:11pt;font-weight:bold;font-style:normal;text-decoration:none;color:rgba(0, 0, 0, 1.00);background-color:transparent;}.cl-67386310{font-family:'Arial';font-size:9pt;font-weight:normal;font-style:normal;text-decoration:none;color:rgba(0, 0, 0, 1.00);background-color:transparent;}.cl-673ce994{margin:0;text-align:center;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);padding-bottom:5pt;padding-top:5pt;padding-left:5pt;padding-right:5pt;line-height: 1;background-color:transparent;}.cl-673d006e{width:1in;background-color:transparent;vertical-align: middle;border-bottom: 0.75pt solid rgba(102, 102, 102, 1.00);border-top: 0.75pt solid rgba(102, 102, 102, 1.00);border-left: 0.75pt solid rgba(102, 102, 102, 1.00);border-right: 0.75pt solid rgba(102, 102, 102, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-673d0078{width:1in;background-color:transparent;vertical-align: middle;border-bottom: 0.75pt solid rgba(102, 102, 102, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0.75pt solid rgba(102, 102, 102, 1.00);border-right: 0.75pt solid rgba(102, 102, 102, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}</style><table data-quarto-disable-processing='true' class='cl-67440ed6'><thead><tr style="overflow-wrap:break-word;"><th class="cl-673d006e"><p class="cl-673ce994"><span class="cl-673862e8">Sepal.Length</span></p></th><th class="cl-673d006e"><p class="cl-673ce994"><span class="cl-673862e8">Sepal.Width</span></p></th><th class="cl-673d006e"><p class="cl-673ce994"><span class="cl-673862e8">Petal.Length</span></p></th><th class="cl-673d006e"><p class="cl-673ce994"><span class="cl-673862e8">Petal.Width</span></p></th><th class="cl-673d006e"><p class="cl-673ce994"><span class="cl-673862e8">Species</span></p></th></tr></thead><tbody><tr style="overflow-wrap:break-word;"><td class="cl-673d0078"><p class="cl-673ce994"><span class="cl-67386310">5.1</span></p></td><td class="cl-673d0078"><p class="cl-673ce994"><span class="cl-67386310">3.5</span></p></td><td class="cl-673d0078"><p class="cl-673ce994"><span class="cl-67386310">1.4</span></p></td><td class="cl-673d0078"><p class="cl-673ce994"><span class="cl-67386310">0.2</span></p></td><td class="cl-673d0078"><p class="cl-673ce994"><span class="cl-67386310">setosa</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">4.9</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">3.0</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">1.4</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">0.2</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">setosa</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">4.7</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">3.2</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">1.3</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">0.2</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">setosa</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">4.6</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">3.1</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">1.5</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">0.2</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">setosa</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">5.0</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">3.6</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">1.4</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">0.2</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">setosa</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">5.4</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">3.9</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">1.7</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">0.4</span></p></td><td class="cl-673d006e"><p class="cl-673ce994"><span class="cl-67386310">setosa</span></p></td></tr></tbody></table></div>
```



