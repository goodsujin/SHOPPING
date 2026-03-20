![ERD 図面](.<img width="1402" height="728" alt="image" src="https://github.com/user-attachments/assets/dc25437c-9825-4128-a36b-6feebba0f9ba" />
)
非会員注文とカートデータロジック考慮したイーコマース設計図案です。

# 🛒 ECサイト データベース設計

非会員注文とカートデータロジックを考慮したイーコマースのデータベース設計プロジェクトです。

## 使用技術
- MySQL

## テーブル構成
- MEMBER_USER : 会員情報
- SELLER : 販売者情報
- PRODUCT : 商品情報
- CATEGORY : カテゴリ情報
- SHOPING_CART : ショッピングカート
- PRODUCT_QUANTITY : 商品数量
- ORDER_ITEM : 注文内訳
- PAYMENT_INFO : 決済情報
- DELIVERY : 配送先情報
- MEMBER_GRADE : 会員等級
- NON_MEMBER : 非会員注文

## 設計のポイント
- SELLER_KEYはNULLを許容。全ての会員が販売者ではないため
- DELIVERY_KEYはNULLを許容。配送先未登録の会員も存在するため
- MEMBER_USERからPAYMENT_KEYを削除。決済情報はPG社連携を想定し直接保存しない設計
- ORDER_ITEMにMEMBER_KEYを追加。一人の会員が複数の注文を持てる構造に変更
- PAYMENT_INFOにMEMBER_KEYを追加。どの会員の決済かを参照できるように変更
