
# 情境
逢甲科技自2020年成立，從事雲端資訊應用與資訊系統委外託管服務。
近期黑貓購物拓展通路從電視電話購物至網路購物，委託將現有資訊系統搬遷到雲端。
然而，公司並沒有過多的資訊人員可以協助雲端搬遷。
因此第一階段討論會議，先將將庫存系統部署在AWS雲端上，後續維運交回給黑貓購物資訊人員進行管理。
請協助逢甲科技進行分析、設計與實體的建置。

以下是客戶在會議中提出的需求

1.網站需要24小時穩定對外開放

2.管理者可以異動網站上的庫存資訊，這些庫存資訊將會集中管理

3.公司沒有過多的伺服器(你可以想像是電腦)可以閒置，但網站伺服器要能因應購物人潮流量。需求峰值期間仍然可以保持高性能


# 實作環境：AWS Academy Cloud Foundation-Sandbox

1.開啟Sandbox

![image](https://user-images.githubusercontent.com/103306835/170182468-2b4bf6d5-8963-4e68-9c8d-fbc267171b1b.png)

2.點選[Start Lab]

![image](https://user-images.githubusercontent.com/103306835/170182498-dbba508b-148c-45c4-901c-d10f71b80f76.png)

3.點選[AWS]

![image](https://user-images.githubusercontent.com/103306835/170182571-caa9224d-fbeb-406f-af3c-d4dccc98d580.png)

4.登入AWS Management Console

![image](https://user-images.githubusercontent.com/103306835/170182604-7e0e16c7-a178-45ab-88eb-8beb8fc69f91.png)

5.實施步驟

![image](https://user-images.githubusercontent.com/103306835/170182628-f2f1dea7-4a79-4689-b6e5-7782266df200.png)


# 任務1：基礎架構實施

目標：進行雲端服務架構的安全性部署

1.基礎架構規劃

![image](https://user-images.githubusercontent.com/103306835/170182776-06044e36-10cf-426c-9a2b-8e48f6902eaf.png)

2.點選[VPC]

![image](https://user-images.githubusercontent.com/103306835/170182820-d701c1fc-ac5e-4e81-bc68-17c5ea1267dd.png)

3.您的VPC

![image](https://user-images.githubusercontent.com/103306835/170182917-989b358f-985c-4acb-9378-cda6e85e02f1.png)

4.點選Work VPC

![image](https://user-images.githubusercontent.com/103306835/170182953-433e8b47-0f49-447d-b270-b6af05c93145.png)

5.改成Lab VPC

![image](https://user-images.githubusercontent.com/103306835/170182979-2d5bf837-7d4b-498a-ba86-5cd164a82b72.png)

6.點選[儲存]

![image](https://user-images.githubusercontent.com/103306835/170182998-88beb920-9faa-44ef-bd49-4824bd9f2816.png)

7.成功更改VPC

![image](https://user-images.githubusercontent.com/103306835/170183208-e9604936-944c-49f4-97fe-b4caedd263ba.png)

8.點選[子網路]

![image](https://user-images.githubusercontent.com/103306835/170183252-7bf9e9a6-cef2-4332-8afc-8001796b7f5b.png)

9.選擇Work Public Subnet

![image](https://user-images.githubusercontent.com/103306835/170183522-145b7351-b587-44f3-be77-fb5cd95e5acd.png)

10.更名為Public Subnet1 並點選儲存

![image](https://user-images.githubusercontent.com/103306835/170183591-97e9de77-ef10-4b2c-a8e7-bfee51caf42c.png)

11.更名成功

![image](https://user-images.githubusercontent.com/103306835/170183623-685612bb-b733-4bf2-b3d0-b370b4ef0c65.png)

12.點選[建立子網路]

![image](https://user-images.githubusercontent.com/103306835/170183726-4f1d9898-465a-4503-b883-aa99c4686b49.png)

13.選擇Lab VPC

![image](https://user-images.githubusercontent.com/103306835/170183753-aab3d636-957d-48b8-a3f4-2cc6f3cb2e6a.png)

14.輸入子網路名稱/可用區域/IPV4 CIDR區塊 Public subnet2(10.0.2.0/24 ；us-east-1b)

![image](https://user-images.githubusercontent.com/103306835/170183812-357d17a6-37e4-408e-8ac6-5942ff70cb92.png)

15.點選[新增子網路]

![image](https://user-images.githubusercontent.com/103306835/170183880-9f1b290b-7b16-48bd-be72-df3af9021d46.png)

16.輸入子網路名稱/可用區域/IPV4 CIDR區塊 Private subnet1(10.0.1.0/24;us-east-1a)

![image](https://user-images.githubusercontent.com/103306835/170184205-e7f8fb62-2a05-4a0f-9f91-bc7bd8d6a03b.png)

17.點選[新增子網路]

![image](https://user-images.githubusercontent.com/103306835/170184290-7336be2a-13d7-4533-9421-812606442fad.png)

18.輸入子網路名稱/可用區域/IPV4 CIDR區塊 Private subnet2(10.0.3.0/24；us-east-1b)

![image](https://user-images.githubusercontent.com/103306835/170184406-58ae1c27-8e32-4cb4-9234-36cbf3e97a2c.png)

19.點選[建立子網路]

![image](https://user-images.githubusercontent.com/103306835/170185203-91df4c1d-eb2d-47c9-93c6-ab40607720f7.png)

20.正在建立子網絡…

![image](https://user-images.githubusercontent.com/103306835/170185248-9f15eca0-4c96-43aa-ba83-22be7bef17af.png)

21.成功新增子網路

![image](https://user-images.githubusercontent.com/103306835/170185441-c0c4daf9-ff77-47c3-acd3-3c66e6c7669c.png)

22.勾選Public Subnet1

![image](https://user-images.githubusercontent.com/103306835/170185558-3abd396c-3a4a-4748-aa09-79a2e32ee7f3.png)

23.點選[動作]

![image](https://user-images.githubusercontent.com/103306835/170185603-5d820cf9-631f-4fbb-b903-388ec03f5cbf.png)

24.點選[編輯子網路設定]

![image](https://user-images.githubusercontent.com/103306835/170185697-70777349-f444-43e7-b986-2472a27ce64c.png)

25.勾選[啟用….]

![image](https://user-images.githubusercontent.com/103306835/170185728-aadba0d5-abdb-4d1a-8ac4-c5e2aeae6f88.png)

26.點選[儲存]

![image](https://user-images.githubusercontent.com/103306835/170185800-2c9a8b84-5d65-4c21-99a9-500dbb27170a.png)

27.完成更新

![image](https://user-images.githubusercontent.com/103306835/170185828-1d754fde-9186-425a-8e46-da1796e5a9dd.png)

28.請參考Public Subnet1 Auto-ip設定進行Public Subnet2 Auto-ip設定

![image](https://user-images.githubusercontent.com/103306835/170185988-2dd41613-a0bd-43a9-aa45-a3bbd321c35e.png)

# 任務2：架設網站伺服器

目標：建立網站伺服器(作業系統：Linux)，並直接部署網站在上面。

1.點選EC2

![image](https://user-images.githubusercontent.com/103306835/170186206-f1c26900-8ea0-4963-8bd7-ada6bb7d4f3a.png)

2.點選[執行個體]

![image](https://user-images.githubusercontent.com/103306835/170186248-faf05b5c-a09b-488a-82f3-14a65c83a67b.png)

3.點選[啟動執行個體]

![image](https://user-images.githubusercontent.com/103306835/170186283-eb03dc7e-612d-4322-ba7c-045abd619d99.png)

4.名稱：WebServer

![image](https://user-images.githubusercontent.com/103306835/170186309-8297d053-6bdd-4631-aae0-2fb3ae6caab6.png)

5.作業系統點選[Amazon Linux]

![image](https://user-images.githubusercontent.com/103306835/170186553-113efbbc-6dc0-4669-a00a-226bdb85feae.png)

6.選擇預設金鑰：vockey

![image](https://user-images.githubusercontent.com/103306835/170186582-e09acb70-0071-4e3b-b098-c20766d709f7.png)

7.點選[編輯]

![image](https://user-images.githubusercontent.com/103306835/170186645-3b8fb8d7-d498-46ad-b8f3-4ce6354783a5.png)

8.選擇Lab VPC

![image](https://user-images.githubusercontent.com/103306835/170186677-e5b5a724-bd98-4979-9dbc-e1571037f00b.png)

9.選擇在us-east-1a的子網

![image](https://user-images.githubusercontent.com/103306835/170186708-9804217a-b67e-4d00-8ed7-0bb2d8fffc1d.png)

10.選擇建立安全群組

![image](https://user-images.githubusercontent.com/103306835/170186743-fc15b34d-5436-4b47-adbe-59072e1c3093.png)

11.命名為WebServer

![image](https://user-images.githubusercontent.com/103306835/170186790-649ceea0-68cd-46cd-8c64-75de035249cb.png)

12.選擇SSH類型 來源：0.0.0.0/0

![image](https://user-images.githubusercontent.com/103306835/170186822-41f3745f-3ea4-48d7-938f-95bbef1ad92f.png)

13.點選[Add security group rule]

![image](https://user-images.githubusercontent.com/103306835/170186872-91de4621-814c-4ed2-96ed-4318f1c0e3f5.png)

