```uml
@startuml



[*] -> トップページ
トップページ --> トップページ : ログアウトをクリック
トップページ --> トップページ : 商品検索する
トップページ --> 商品詳細 : 商品をクリック
トップページ -up-> 会員情報 : 会員情報をクリック
トップページ --> ログイン : ログインをクリック
トップページ --> カート内 : カートの中をクリック
トップページ:do/商品説明一覧を表示
トップページ --> 各SNS : 各SNSのアイコンをクリック
トップページ --> お問い合わせ :お問い合わせをクリック



state 会員情報{
[*] -> 会員情報ページ
会員情報ページ --> 会員情報変更 : 会員情報変更クリック
会員情報変更 -up-> 会員情報ページ: 変更するをクリック/戻るをクリック
}
会員情報 --> トップページ : トップページをクリック/商品検索する





商品詳細 --> カート内 : カートをクリック
商品詳細 --> トップページ : 前の画面に戻るをクリック
商品詳細:do/商品説明を表示



state カート内{
[*] -> カート
カート --> 注文 : 注文をクリック
カート --> カート : 数量を変更/商品を削除
注文 --> カート : カートをクリック
state 注文{
[*] --> お届け先入力
お届け先入力 -> お届け先入力内容確認 : 入力内容確認をクリック
お届け先入力内容確認 -> お届け先入力 : 修正をクリック
お届け先入力内容確認 -> 購入完了 : 注文確定をクリック
}
}
カート内 -up-> トップページ : トップページをクリック/商品を検索する
カート内 -up-> トップページ : ログアウトをクリック
カート内 --> 商品詳細 : 商品をクリックする




state ログイン{
[*]->ログインページ
ログインページ --> 会員情報登録 : 会員登録はこちらをクリック
state 会員登録{
会員情報登録 --> メール送信完了 : 登録するをクリック
メール送信完了 :do/メールを送信しましたを表示
[*] -> 登録完了 : メールにあるurlをクリック
会員登録 --> ログインページ : 登録完了後ご利用はこちらからをクリック
}
}
ログイン -> トップページ : トップページをクリック/商品検索する/ログイン完了後



state お問い合わせ{
[*] -> お問い合わせページ
お問い合わせページ -> お問い合わせ完了 :送信をクリック
お問い合わせ完了 -left-> お問い合わせページ : 戻るクリック
}
お問い合わせ -left-> トップページ : トップページをクリック

@enduml



```
