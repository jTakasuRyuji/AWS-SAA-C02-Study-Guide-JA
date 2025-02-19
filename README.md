# AWS SAA-C02 学習ガイド
このスタディガイドは、新しい AWS 認定ソリューションアーキテクト - アソシエイト試験に合格するために役立ちます。このガイドを参照しながら、以下の内容を学習するのが理想的です：

  1. Stephane Maarek's <a href="https://links.datacumulus.com/aws-certified-sa-associate-coupon">Ultimate AWS Certified Solutions Architect Associate 2021 course</a> (permanent discount available through this link) or A Cloud Guru's <a href="https://acloud.guru/learn/aws-certified-solutions-architect-associate">AWS Certified Solutions Architect Associate SAA-C02 course</a>
  2. The FAQs for the most critical services, included in the recommended reading list below
  3. Tutorials Dojo's <a href="https://www.udemy.com/course/aws-certified-solutions-architect-associate-amazon-practice-exams-saa-c02/">AWS Certified Solutions Architect Associate Practice Exams </a>
  4. Andrew Brown's <a href="https://www.youtube.com/watch?v=Ia-UEYYR44s">AWS Certified Solutions Architect - Associate 2020 (PASS THE EXAM!) | Ad-Free Course
</a> 

*Notes*:
どこかの時点で、自分の進捗状況に不確実性があり、さらに時間が必要であると感じた場合は、AWS 試験日を延期することができます。 Be sure to also keep up with the ongoing discussions in <a href="https://reddit.com/r/AWSCertifications/">r/AWSCertifications</a> as you will find relevant exam tips, studying material, and advice from other exam takers. Before experimenting with AWS, it's very important to be sure that you know what is <a href="https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc">free</a> and what isn't. Relevant Free Tier FAQs can be found <a href="https://aws.amazon.com/free/free-tier-faqs/">here</a>. 最後に、Udemy はコースを随時セールにしていることがよくあります。コンテンツがどれだけ緊急に必要かに応じて、Tutorial Dojo 模擬試験または Stephane Maarek のコースのいずれかを購入するのを待つ価値があるかもしれません。



## Table of Contents
1. <a href="#introduction">Introduction</a>

2. <a href="#identity-access-management-iam">Identity Access Management (IAM)</a>

3. <a href="#simple-storage-service-s3">Simple Storage Service (S3)</a>

4. <a href="#cloudfront">CloudFront</a>

5. <a href="#snowball">Snowball</a>

6. <a href="#storage-gateway">Storage Gateway</a>

7. <a href="#elastic-compute-cloud-ec2">Elastic Compute Cloud (EC2)</a>

8. <a href="#elastic-block-store-ebs">Elastic Block Store (EBS)</a>

9. <a href="#elastic-network-interfaces-eni">Elastic Network Interfaces (ENI)</a>

10. <a href="#security-groups">Security Groups</a>

11. <a href="#web-application-firewall-waf">Web Application Firewall (WAF)</a>

12. <a href="#cloudwatch">CloudWatch</a>

13. <a href="#cloudtrail">CloudTrail</a>

14. <a href="#elastic-file-system-efs">Elastic File System (EFS)</a>

15. <a href="#amazon-fsx-for-windows">Amazon FSx for Windows</a>

16. <a href="#amazon-fsx-for-lustre">Amazon FSx for Lustre</a>

17. <a href="#relational-database-service-rds">Relational Database Service (RDS)</a>

18. <a href="#aurora">Aurora</a>

19. <a href="#dynamodb">DynamoDB</a>

20. <a href="#redshift">Redshift</a>

21. <a href="#elasticache">ElastiCache</a>

22. <a href="#route53">Route53</a>

23. <a href="#elastic-load-balancers-elb">Elastic Load Balancers (ELB)</a>

24. <a href="#auto-scaling">Auto Scaling</a>

25. <a href="#virtual-private-cloud-vpc"> Virtual Private Cloud (VPC)</a>

26. <a href="#simple-queuing-service-sqs"> Simple Queuing Service (SQS)</a>

27. <a href="#simple-workflow-service-swf"> Simple Workflow Service (SWF)</a>

28. <a href="#simple-notification-service-sns"> Simple Notification Service (SNS)</a>

29. <a href="#kinesis"> Kinesis </a>

30. <a href="#lambda"> Lambda </a>

31. <a href="#api-gateway"> API Gateway </a>

32. <a href="#cloudformation">CloudFormation </a>

33. <a href="#cloudformation">ElasticBeanstalk</a>

34. <a href="#aws-organizations">AWS Organizations</a>

35. <a href="#miscellaneous">Miscellaneous</a>



## Introduction

<a href="https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS-Certified-Solutions-Architect-Associate-Exam-Guide_v1.1_2019_08_27_FINAL.pdf">**The official AWS Solutions Architect - Associate (SAA-C02) exam guide**</a>

**編注**日本語版ドキュメントは以下の通り：
<a href="https://d1.awsstatic.com/ja_JP/training-and-certification/docs-sa-assoc/AWS-Certified-Solutions-Architect-Associate-Exam-Guide_v1.1_2019_08_27_FINAL.pdf">**AWS 認定ソリューションアーキテクト - アソシエイト (SAA-C02)  試験ガイド**</a>

### Exam Content Breakdown:
![image](https://github.com/jTakasuRyuji/AWS-SAA-C02-Study-Guide-JA/assets/8042749/23673040-d368-4894-a05f-cc8c83d508aa)

#### 分野 1: レジリエントアーキテクチャの設計 

 1.1 多層アーキテクチャソリューションの設計 

 1.2 可用性の高いアーキテクチャやフォールトトレラントなアーキテクチャの設計 

 1.3 AWS のサービスを使用したデカップリングメカニズムの設計 

 1.4 適切な回復力のあるストレージの選択 


#### 分野 2: 高パフォーマンスアーキテクチャの設計 

 2.1 ワークロードに対する伸縮自在でスケーラブルな**コンピューティング**ソリューションの識別 

 2.2 ワークロードに対するパフォーマンスとスケーラブルな**ストレージ**ソリューションの選択 

 2.3 ワークロードに対するパフォーマンスが高い**ネットワーキング**ソリューションの選択 

 2.4 ワークロードに対するパフォーマンスの高い**データベース** ソリューションの選択 


#### 分野 3: セキュアなアプリケーションとアーキテクチャの設計

 3.1 AWS リソースへのセキュアなアクセスの設計 

 3.2 セキュアなアプリケーション階層の設計 

 3.3 適切なデータセキュリティオプションの選択 


#### 分野 4: コスト最適化アーキテクチャの設計 

 4.1 コスト効率が高い**ストレージ**ソリューションの識別 

 4.2 コスト効率が高い**コンピューティング**および**データベース** サービスの識別 

 4.3 コスト最適化**ネットワーク**アーキテクチャの設計 



### Recommended Reading:

すでに知っていること、あるいは真実であると推測できることをざっと目を通すことで、多くの分野をカバーすることができる。特に、各段落の最初の文章を読み、その文章で言われていることに不明な点がなければ、次の段落の最初の文章に進む。必要に応じてメモを取る。

  1. <a href="https://docs.aws.amazon.com/wellarchitected/latest/framework/wellarchitected-framework.pdf">AWS Well-Architected Framework</a>

  2. <a href="https://aws.amazon.com/vpc/faqs/">Amazon VPC FAQs</a>

  3. <a href="https://aws.amazon.com/autoscaling/faqs/"> AWS Autoscaling FAQs</a>

  4. <a href="https://aws.amazon.com/ec2/faqs/">Amazon EC2 FAQs</a>

  5. <a href="https://aws.amazon.com/ec2/autoscaling/faqs/"> Amazon EC2 Auto Scaling FAQs </a>

  6. <a href="https://aws.amazon.com/ebs/faqs/">Amazon EBS FAQs</a>

  7. <a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html"> Elastic network interfaces</a>

  8. <a href="https://aws.amazon.com/s3/faqs/">Amazon S3 FAQs</a> 
  
  9. <a href="https://aws.amazon.com/elasticloadbalancing/faqs/"> Elastic Load Balancing FAQs</a>

  10. <a href="https://aws.amazon.com/route53/faqs/"> Amazon Route 53 FAQs</a>

  11. <a href="https://aws.amazon.com/storagegateway/faqs/"> AWS Storage Gateway FAQs</a>

  12. <a href="https://aws.amazon.com/efs/faq/"> Amazon EFS FAQs</a>

  13. <a href="https://aws.amazon.com/fsx/windows/faqs/">Amazon FSx for Windows File Server FAQs</a>

  14. <a href="https://aws.amazon.com/fsx/lustre/faqs/">Amazon FSx for Lustre FAQs</a>
  
  15. <a href="https://aws.amazon.com/organizations/faqs/">AWS Organizations FAQs</a>

## Identity Access Management (IAM)

### IAM の概要:

IAMは、AWS内の集中管理ハブを提供し、他のすべてのAWSサービスと統合する。IAMは、様々なアクセス許可レベルでアクセスを共有する機能を備えており、一時的または限定的なアクセスのためにIDフェデレーション（FacebookやGoogleのような信頼できる外部パーティに認証を委譲するプロセス）を使用する機能をサポートしている。IAMはMFAをサポートし、組織全体でカスタムパスワードローテーションポリシーを設定することができます。
また、PCI DSS（ペイメントカード業界のデータセキュリティ基準）にも準拠している。(政府が定めたクレジットカードのセキュリティ規制をクリアしています。）

### IAM Entities:

**ユーザー** - 従業員、システム・アーキテクト、CTOなど、個々のエンド・ユーザー。

**グループ** - システム管理者、人事担当者、財務チームなど、権限を共有する類似した人々の集まり。指定されたグループ内の各ユーザーは、グループに設定された権限を継承します。

**ロール** - AWS LambdaがS3への書き込みパーミッションを必要としたり、EC2インスタンス群がRDS MySQLデータベースからの読み取りパーミッションを必要とするなど、仕事をするためにパーミッションを付与される必要があるソフトウェアサービス。

**ポリシー** - アクセスを許可または制限するために適用される、文書化されたルールセット。ユーザー、グループ、ロールが適切にパーミッションを設定するには、ポリシーを使用する。ポリシーはJSONで記述され、特定のニーズに合わせてカスタムポリシーを使用するか、AWSによって設定されたデフォルトポリシーを使用することができる。

![Screen Shot 2020-06-06 at 10 49 48 PM](https://user-images.githubusercontent.com/13093517/83959193-11533980-a848-11ea-9d03-d8133e0aaa86.png)

IAMポリシーはIAM IDではないため、上記の他のエンティティとは区別される。代わりに、IAM Identityに添付され、当該IAM Identityが必要な機能を実行できるようにする。

### IAM の詳細:

- IAMはリージョンに制限されないグローバルなAWSサービスである。どのようなユーザー、グループ、ロール、ポリシーでもグローバルにアクセスできる。

- 完全な管理者アクセスを持つルートアカウントは、AWSにサインアップするために使用されるアカウントである。したがって、使用するAWSアカウントを作成するために使用するメールアドレスは、おそらく会社の公式メールアドレスであるべきだ。

- 新規ユーザーは、アカウントが最初に作成されたとき、何の権限も持っていません。これは、パーミッションを意図的に付与する必要があるため、アクセスを委譲する安全な方法です。

- 初めてAWSエコシステムに参加する場合、プログラムアクセスを付与する際に、新規ユーザーにはアクセスキーIDとシークレットアクセスキーIDが提供されます。これらは新規ユーザーが参加するために特別に一度だけ作成されるため、紛失した場合は新しいアクセスキーIDとシークレットアクセスキーIDを生成するだけです。アクセスキーは AWS CLI と SDK でのみ使用されるので、コンソールへのアクセスには使用できません。

- AWSアカウントを作成する際、シングルサインオン(SSO)を提供する社内の既存のIDプロバイダがあるかもしれません。このような場合、AWS 上で既存の ID を再利用することは便利で効率的であり、完全に可能です。これを行うには、IAMロールをActive Directoryの1つに引き受けさせる。これは、IAM IDフェデレーション機能によって、外部サービスがIAMロールを引き受けることができるようになるからだ。

- IAMロールは、EC2インスタンスのようなサービスに、最初の使用/作成前、または使用/作成後に割り当てることができる。パーミッションは何度でも変更できる。これはすべてAWSコンソールとAWSコマンドラインツールの両方を使用して行うことができる。

- IAMグループをネストすることはできない。個々の IAM ユーザーは複数のグループに属することができるが、ある IAM グループを別の IAM グループの中に埋め込むようにサブグループを作成することはできない。

- IAMポリシーでは、どのリソースに誰がアクセスできるかを定義するタグを簡単に追加できる。これらのタグを使用して、特定のIAMポリシーでアクセスを制御する。例えば、本番用EC2インスタンスと開発用EC2インスタンスには、このようなタグを付けることができる。これにより、開発用インスタンスにしかアクセスできないはずの人が本番用インスタンスにアクセスできないようにすることができる。 

### IAMの優先レベル
- **Explicit Deny** (明示的拒否)： 特定のリソースへのアクセスを拒否し、この裁定を覆すことはできない。

-**Explicit Allow**: 特定のリソースへのアクセスを許可する： 明示的拒否(Explicit Deny)**: 特定のリソースへのアクセスを許可する。

- **Default Deny (またはImplicit Deny)**： IAM IDはリソースにアクセスできない状態で開始する。代わりにアクセスを許可する必要があります。

### IAM セキュリティツール：
   **IAM Access Advisor(ユーザー・レベル)
- アクセス・アドバイザーは、ユーザーに付与されたサービス権限と、それらのサービスが最後にアクセ スされた日時を表示します。
- この情報を使用して、ポリシーを修正できます。

  **IAM 資格情報レポート(アカウントレベル)
- すべてのアカウントユーザーとその各種資格情報のステータスを一覧表示するレポートです。


## Simple Storage Service (S3)

### S3 の概要:
S3は、開発者とITチームに、安全で耐久性があり、拡張性の高いオブジェクトストレージを提供する。オブジェクトストレージは、ブロックストレージとは対照的に、3つのもので構成されるデータを指す一般的な用語である：

  1.) 保存したいデータ

  2.) 拡張可能な量のメタデータ

  3.) データを検索できる一意の識別子 

このため、ファイルやディレクトリをホストするには最適で、データベースやオペレーティング・システムをホストするには不向きである。次の表は、オブジェクト・ストレージとブロック・ストレージの主な違いを示している：

![Screen Shot 2020-06-05 at 3 34 57 PM](https://user-images.githubusercontent.com/13093517/83915925-352c5780-a742-11ea-975b-53d4e5d07e7c.png)


S3にアップロードされたデータは、複数のファイルや施設に分散される。S3にアップロードされるファイルの上限は1ファイルあたり5TBで、アップロード可能なファイル数は事実上無限である。すべてのファイルを格納するS3バケットはユニバーサルネームスペースで命名されるため、一意性が要求される。アップロードに成功すると、すべてHTTP 200レスポンスが返されます。

### S3 の詳細:
- オブジェクト (通常のファイルまたはディレクトリ) は、キー、値、バージョン ID、メタデータとともに S3 に保存されます。これらには、基本的にオブジェクト自体に対する権限であるアクセス制御リストのトレントやサブリソースも含めることができます。
- S3 のデータ整合性モデルにより、最初の PUT リクエスト後の新しいオブジェクトへの即時読み取りアクセスが保証されます。これらの新しいオブジェクトは AWS に初めて導入されるため、どこでも更新する必要がないため、すぐに利用できるようになります。
- S3 のデータ整合性モデルにより、既存のオブジェクトの PUTS および DELETES に対する即時読み取りアクセスも保証されます。<a href="https://aws.amazon.com/fr/about-aws/whats-new/2020/12/ amazon-s3-now-delivers-strong-read-after-write-consistency-automatically-for-all-applications/">2020 年 12 月以降</a>。
- Amazon は、冗長性削減ストレージ クラスを除くすべての S3 ストレージ クラスに対して 99.999999999% (または 11 9 秒) の耐久性を保証します。
- S3 には次の主な機能が搭載されています。

  1.) ストレージの階層化と価格変動

  2.) 古いコンテンツを失効させるライフサイクル管理

  3.) バージョン管理のためのバージョニング

  4.) プライバシーのための暗号化

  5.) コンテンツの偶発的または悪意のある削除を防ぐためのMFA削除

  6.) データを保護するためのアクセス制御リストとバケットポリシー

- S3の料金

  1.) ストレージサイズ

  2.) リクエスト数

  3.) ストレージ管理価格（ティアと呼ばれる）

  4.) データ転送価格（インターネット経由でAWSを出たり入ったりするオブジェクト）

  5.) 転送アクセラレーション（Cloudfront経由でオブジェクトを移動する際のオプションの高速化）

  6.) クロスリージョンレプリケーション（デフォルトで提供されている以上のHA）

- バケットポリシーはバケットレベルでデータを保護し、アクセスコントロールリストはより細かいオブジェクトレベルでデータを保護します。
- デフォルトでは、新しく作成されたバケットは全てプライベートです。
- S3はアクセスログを作成するように設定することができ、そのログは現在のアカウントにある別のバケット、あるいは別のアカウントに保存することができる。これにより、S3内で誰が何にアクセスしたかを簡単に監視できる。
- AWSアカウント間でS3バケットを共有するには3つの異なる方法がある：

  1.) IAM & Bucket Policiesを使ってバケット全体を共有する。

  2.) プログラムアクセスのみで、ACLとBucket Policiesを使ってオブジェクトを共有する。

  3.) コンソールとターミナル経由のアクセスには、クロスアカウントIAMロールを使う

- S3は静的ウェブサイトのホスティングに最適です。S3で静的ウェブサイトホスティングを有効にすると、index.htmlファイルとerror.htmlファイルの両方が必要になる。静的ウェブサイトホスティングは、インターネット経由でアクセスできるウェブサイトのエンドポイントを作成します。
- 新しいファイルをアップロードし、バージョン管理を有効にすると、以前のバージョンのプロパティは継承されません。

### S3 Storage Classes:
**S3 Standard** - 99.99%の可用性と11 9sの耐久性。このクラスのデータは、複数の施設の複数のデバイスに冗長的に保存され、同時に2つのデータセンターの障害に耐えられるように設計されています。

**S3 Infrequently Accessed (IA)** - 必要な頻度は低いが、必要なときに素早く利用できるデータ用。保管料は安いが、検索には料金がかかる。

**S3 One Zone Infrequently Accessed（従来のRRS/Reduced Redundancy Storageの改良版）** - IAの低コストが必要だが、高可用性は必要ない場合。高可用性（HA）を必要としないため、さらに安価です。

**S3インテリジェント・ティアリング** - 組み込みのML/AIを使用して、最も費用対効果の高いストレージクラスを決定し、データを自動的に適切な階層に移動します。運用上のオーバーヘッドやパフォーマンスへの影響はありません。

**S3 Glacier** - データ・アーカイブ用の低コストのストレージ・クラス。このクラスは、検索があまり必要とされない純粋な保存用である。検索時間は数分から数時間です。デフォルトの検索時間をどの程度許容できるかによって、検索方法が異なります：

    迅速： 1～5分ですが、このオプションは最も高額です。
    標準：復元に3～5時間かかります。
    バルク：5～12時間。このオプションは最もコストが低く、大規模なデータセットに適しています。

上記のExpeditedの期間は、AWS全体で異常に需要が高い稀な状況では長くなる可能性があります。どのような状況においてもGlacierデータへの迅速なアクセスが絶対に必要な場合は、*Provisioned Capacity*を購入する必要があります。Provisioned Capacityは、Expedited検索が常に1～5分の時間制約内で動作することを保証します。

**S3 Deep Glacier** - 最も低コストのS3ストレージで、検索には12時間かかる。

<img width="1246" alt="storage_types" src="https://user-images.githubusercontent.com/13093517/83919060-e1247180-a747-11ea-9336-e92ee163ac7a.png">

### S3 Encryption:
S3データは、転送中と静止時の両方で暗号化できる。

**転送中の暗号化**： あるエンドポイントから別のエンドポイント間を通過するトラフィックが解読不可能な場合。サーバーAとサーバーBの間を盗聴する者は、通過する情報を理解することができない。S3のトランジットにおける暗号化は、常にSSL/TLSによって達成される。

**Encryption At Rest**： S3内の不動データが暗号化されている場合。誰かがサーバーに侵入しても、そのサーバー内の暗号化された情報にアクセスすることはできない。静止時の暗号化は、サーバーサイドかクライアントサイドのどちらかで行われる。サーバーサイドとは、S3がデータをディスクに書き込む際に暗号化し、アクセス時に復号化することです。クライアントサイドは、あなたが個人的にオブジェクトを暗号化し、その後S3にアップロードすることです。

AWSがサポートするサーバーサイドでは、以下の方法で暗号化できる：
- S3 Managed Keys / SSE - S3 (server side encryption S3 )** - Amazonが自動的に暗号化と復号鍵を管理する場合。このシナリオでは、使いやすさと引き換えに、アマゾンに若干のコントロールを譲ることになる。
- AWS鍵管理サービス/SSE - KMS** - アマゾンとあなたの両方が暗号化と復号化の鍵を一緒に管理する場合。
- Server Side Encryption w/ customer provided keys / SSE - C** - 自分が管理する自分の鍵をアマゾンに渡す場合。このシナリオでは、より多くのコントロールと引き換えに、使いやすさを譲歩することになる。

### S3 Versioning:
- バージョニングが有効な場合、S3は全ての書き込みや削除を含むオブジェクトの全てのバージョンを保存する。
- コンテンツを暗黙のうちにバックアップし、人為的なミスがあった場合に簡単にロールバックできる素晴らしい機能だ。
- これはGitに似ていると考えることができる。
- 一度バケツでバージョニングを有効にすると、無効にすることはできません。
- バージョニングはライフサイクルルールと統合されているので、バージョンに基づいてデータを期限切れにしたり移行したりするルールを設定することができます。
- バージョニングにはMFA削除機能もあり、さらなるセキュリティレイヤーを提供する。

### S3 ライフサイクル管理：
- 異なるストレージ層間のオブジェクトの移動を自動化する。
- バージョニングと併用可能。
- ライフサイクルルールはオブジェクトの現在のバージョンと以前のバージョンの両方に適用できる。

### S3 クロスリージョンレプリケーション：
- クロスリージョンレプリケーションはバージョニングが有効な場合にのみ機能する。
- クロスリージョンレプリケーションが有効な場合、既存のデータは転送されません。元のバケットへの新規アップロードのみがレプリケートされます。それ以降の更新はすべてレプリケートされます。
- あるバケットの内容を別のバケットにレプリケートするとき、必要であればコンテンツの所有者を実際に変更することができます。また、複製されたコンテンツのある新しい Bucket のストレージ階層を変更することもできます。
- 元の Bucket でファイルが削除された場合（バージョン管理によって真の削除ができないため、削除マーカーによって）、その削除はレプリケートされません。

### S3転送アクセラレーション：
- 転送アクセラレーションは、オリジンでの遅いアップロードやダウンロードではなく、CDNが存在するポイント（エッジロケーションと呼ばれる）でデータを送受信することで、CloudFrontネットワークを利用します。
- これは、バケット自体ではなく、エッジロケーションの個別のURLにアップロードすることで達成されます。これは、AWSネットワークバックボーン上でより高速に転送されます。
- <a href="https://s3-accelerate-speedtest.s3-accelerate.amazonaws.com/en/accelerate-speed-comparsion.html">You can test transfer acceleration speed directly in comparison to regular uploads.</a>

### S3 イベント通知：
Amazon S3の通知機能により、バケット内で特定のイベントが発生した際に通知を受信・送信することができます。通知を有効にするには、まず Amazon S3 に発行させたいイベント（新しいオブジェクトが追加された、古いオブジェクトが削除されたなど）と、Amazon S3 にイベント通知を送信させたい宛先を設定する必要があります。Amazon S3はイベントを発行できる以下の送信先をサポートしています：
- Amazon Simple Notification Service (Amazon SNS)** - 購読しているエンドポイントやクライアントへのメッセージの配信や送信を調整、管理するウェブサービス。
- Amazon Simple Queue Service (Amazon SQS)** - SQS は、コンピュータ間を移動するメッセージを格納するための、信頼性が高くスケーラブルなホステッドキューを提供します。
- AWS Lambda** - AWS Lambdaは、あなたがコードをアップロードすることができ、サービスがAWSインフラストラクチャを使用してあなたに代わってコードを実行することができる計算サービスです。Lambda関数を作成する際に、カスタムコードをパッケージ化してAWS Lambdaにアップロードする。Lambda関数をトリガーするS3イベントは、コードの入力としても機能する。

### S3とElasticSearch：
- ログファイルの保存にS3を使用している場合、ElasticSearchはログの完全な検索機能を提供し、S3バケットに保存されたデータの検索に使用できます。
- ElasticSearchドメインをS3やLambdaと統合することができます。このセットアップでは、S3が受信した新しいログがLambdaへのイベント通知をトリガーし、Lambdaが新しいログデータに対してアプリケーションコードを実行します。コードが処理を終えると、データはElasticSearchドメインにストリーミングされ、観察できるようになります。

### Maximizing S3 Read/Write Performance:
- S3へのオブジェクトの読み書きのリクエストレートが非常に高い場合、パフォーマンスを向上させるために、プレフィックスに日付ベースのシーケンシャルネーミングを使用することができます。以前のバージョンのAWS Docsでは、オブジェクト名のプレフィックスにハッシュキーやランダムな文字列を使うことも提案されていた。 このような場合、オブジェクトの保存に使用されるパーティションがより分散されるため、オブジェクトの読み取り/書き込みパフォーマンスが向上します。
- S3のデータがユーザーから多くのGETリクエストを受けている場合、パフォーマンス最適化のためにAmazon CloudFrontの使用を検討すべきである。CloudFrontをS3と統合することで、CloudFrontのキャッシュを経由してコンテンツをユーザーに配信し、より低いレイテンシと高いデータ転送レートを実現することができます。また、S3への直接リクエストを減らすことができるため、コスト削減にもつながります。例えば、非常に人気のあるオブジェクトがいくつかあるとします。CloudFrontはそれらのオブジェクトをS3からフェッチし、キャッシュする。CloudFrontはキャッシュからオブジェクトに対する将来のリクエストに対応し、Amazon S3に送信するGETリクエストの総数を減らすことができます。
- <a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/request-rate-perf-considerations.html "> More information on how to ensure high performance in S3</a>

### S3 Server Access Logging:
- サーバアクセスログは、バケツへのリクエストの詳細な記録を提供します。サーバアクセスログは多くの用途に有用です。例えば、アクセスログ情報はセキュリティやアクセス監査に役立ちます。また、顧客ベースについて学び、Amazon S3の請求額をよりよく理解するのにも役立ちます。
- デフォルトでは、ロギングは無効になっています。ロギングが有効な場合、ログはソースバケットと同じAWSリージョンのバケットに保存されます。
- 各アクセスログレコードは、単一のアクセスリクエストに関する詳細、例えばリクエスト元、バケット名、リクエスト時間、リクエストアクション、レスポンスステータス、関連する場合はエラーコードを提供します。
- 仕組みは以下の通り：
   - S3は監視したいバケットのアクセスログレコードを定期的に収集します。
   - S3はそれらのレコードをログファイルに統合します。
   - S3は最終的にログファイルをログオブジェクトとしてセカンダリ監視バケットにアップロードします。

### S3 Multipart Upload:
- マルチパートアップロードでは、1つのオブジェクトをパーツのセットとしてアップロードできます。各部分はオブジェクトのデータの連続した部分です。これらのオブジェクト パーツは独立して、任意の順序でアップロードできます。
- マルチパートアップロードは 100 MB を超えるファイルに推奨され、5 GB を超えるファイルをアップロードする唯一の方法です。マルチパートアップロードは、データを並行してアップロードすることで効率を高め、機能性を実現します。
- いずれかの部分の送信が失敗しても、他の部分に影響を与えることなく、その部分を再送信できます。オブジェクトのすべての部分がアップロードされた後、Amazon S3はこれらの部分を組み立て、オブジェクトを作成します。
- マルチパートアップロードを使いたい理由として考えられること：
  - マルチパートアップロードは、最終的なオブジェクトサイズを知る前にアップロードを開始する能力を提供します。
  - マルチパートアップロードはスループットを向上させます。
  - マルチパートアップロードは、オブジェクトのアップロードを一時停止および再開する機能を提供します。
  - マルチパートアップロードは、ネットワーク問題からの迅速な回復を実現します。
- AWS SDKを使用して、オブジェクトを分割してアップロードできます。あるいは、AWS CLI経由で同じアクションを実行することもできます。
- また、**バイトレンジフェッチ**を使用してS3からのダウンロードを並列化することもできます。ダウンロード中に障害が発生した場合、その障害はオブジェクト全体ではなく、特定のバイト範囲にのみ局所化されます。

### S3 Pre-signed URLs:
- 全てのS3オブジェクトはデフォルトではプライベートであるが、プライベートオブジェクトを持つプライベートバケットのオブジェクトオーナーは、バケットのパーミッションをパブリックに変更することなく、オプションでそれらのオブジェクトを共有することができる。
- これは、事前に署名されたURLを作成することによって行われる。自分のセキュリティ認証情報を使って、プライベートなS3オブジェクトのダウンロードや閲覧を期間限定で許可することができる。
- S3オブジェクトの署名済みURLを作成する際には、以下のことを行う必要があります：
  - セキュリティ認証情報を提供する。
  - バケットを指定する。
  - オブジェクトキーを指定する。
  - HTTPメソッドを指定する（オブジェクトをダウンロードするにはGET）。
  - 有効期限を指定する。
  
- 署名済みURLは指定された期間だけ有効で、その期間内に署名済みURLを受け取った人は誰でもそのオブジェクトにアクセスできる。
- 次の図は、事前署名付きURLがどのように機能するかを示しています：

![Screen Shot 2020-06-09 at 8 20 53 PM](https://user-images.githubusercontent.com/13093517/84213482-c6773300-aa8e-11ea-84a1-3c17e14197bc.png)

### S3 Select:
- S3セレクトは、オブジェクトから必要なデータだけを取り出すように設計されたAmazon S3の機能で、S3内のデータにアクセスする必要があるアプリケーションのパフォーマンスを劇的に向上させ、コストを削減することができる。
- ほとんどのアプリケーションは、オブジェクト全体を取得し、さらに分析するために必要なデータのみをフィルタリングする必要があります。S3 Selectによって、アプリケーションはオブジェクト内のデータのフィルタリングとアクセスという重労働をAmazon S3サービスにオフロードすることができる。
- 例として、あなたが大手小売企業の開発者で、1つの店舗の週間売上データを分析する必要があるが、200店舗すべてのデータが毎日新しいGZIP処理されたCSVに保存されているとします。
  - S3 Selectがなければ、必要なデータを取得するために、CSV全体をダウンロード、解凍、処理する必要がある。
  - S3 Selectを使用すると、オブジェクト全体を取得する代わりに、単純なSQL式を使用して、興味のあるストアのデータのみを返すことができます。
- アプリケーションで読み込んで処理しなければならないデータ量を減らすことで、S3 SelectはS3から頻繁にデータにアクセスするほとんどのアプリケーションのパフォーマンスを最大400%向上させることができる。
- また、GlacierでもS3 Selectを使用できる。


## CloudFront

### CloudFront の概要:
AWSのCDNサービスはCloudFrontと呼ばれている。アプリケーションのグローバルパフォーマンスを向上させるために、キャッシュされたコンテンツやアセットを提供する。CloudFrontの主なコンポーネントは、エッジロケーション（キャッシュエンドポイント）、オリジン（EC2インスタンス、S3バケット、Elastic Load Balancer、Route 53コンフィグなど、キャッシュされる真実のオリジナルソース）、ディストリビューション（オリジンからのエッジロケーションの配置、基本的にはネットワークそのもの）である。

### CloudFront の詳細:
- コンテンツがキャッシュされる場合、TTL（Time To Live）と呼ばれる一定の制限時間が設定されます。
- 必要に応じて、CloudFrontは動的、静的、ストリーミング、インタラクティブなコンテンツを含むウェブサイト全体を提供することができます。
- リクエストは常にルーティングされ、ユーザーに最も近いエッジロケーションにキャッシュされるため、CDNノードが伝播し、将来のリクエストに対して最高のパフォーマンスが保証される。
- 配信には2つのタイプがあります： 
  - **ウェブ配信**：ウェブサイト、通常のキャッシュアイテムなど
  - **RTMP**：ストリーミング・コンテンツ、アドビなど
- エッジロケーションは読み取り専用ではない。それらは書き込むことができ、書き込んだ値を元に戻すことができる。
- キャッシュされたコンテンツは手動で無効にしたり、TTLを超えてクリアすることができますが、これにはコストがかかります。
- 特定のオブジェクトやディレクトリ全体の配布を無効にすることで、コンテンツが毎回オリジンから直接読み込まれるようにすることができます。コンテンツの無効化は、オリジンからプルされたコンテンツが正しいように見えても、同じコンテンツをエッジロケーションからプルすると正しくないように見える場合のデバッグ時にも役立ちます。
- オリジンのフェイルオーバーを設定するには、内部に2つのオリジンを持つオリジングループを作成します。1つのオリジンがプライマリ、もう1つがセカンダリとして機能します。プライマリーオリジンに障害が発生すると、CloudFrontは自動的に2つのオリジンを切り替えます。
- PCIやHIPAAに準拠したワークロードを実行しており、使用データをログに記録する必要がある場合は、次のようにします：
    - CloudFrontのアクセスログを有効にする。
    - CloudFront APIに送信されたリクエストをキャプチャする。
- オリジンアクセスアイデンティティ（Origin Access Identity：OAI）は、CloudFront経由でプライベートコンテンツを共有するために使用されます。OAIは、CloudFrontディストリビューションにオリジン（例えばS3バケット）からプライベートオブジェクトを取得する許可を与えるために使用される仮想ユーザーです。

### CloudFrontの署名付きURLと署名付きクッキー：
- CloudFrontの署名付きURLと署名付きクッキーは同じ基本機能を提供します。これらの機能が存在するのは、インターネット経由でコンテンツを配信する多くの企業が、ドキュメント、ビジネスデータ、メディアストリーム、または特定のユーザー向けのコンテンツへのアクセスを制限したいからです。例えば、料金を支払ったユーザーはプライベートコンテンツにアクセスでき、無料層のユーザーはアクセスできないようにする必要があります。
- CloudFrontを通じてプライベートコンテンツを提供したい場合、署名付きURLと署名付きCookieのどちらを使うか決めかねているのであれば、以下を検討してください：
  - 以下の場合は署名付きURLを使用してください：
    - RTMPディストリビューションを使用したい。署名付きクッキーはRTMPディストリビューションではサポートされていません。
    - アプリケーションのインストール・ダウンロードなど、個々のファイルへのアクセスを制限したい。
    - ユーザがCookieをサポートしないクライアント（例えば、カスタムHTTPクライアント）を使用している。
  - 次のような場合は、署名付きクッキーを使用してください：
    - 複数の制限付きファイルへのアクセスを提供したい。たとえば、HLS 形式のビデオのすべてのファイルや、ウェブサイトの有料ユーザー エリア内のすべてのファイルなどです。
    - 現在の URL を変更したくない場合。

## Snowball

### Snowball の概要:
Snowballは、大量のデータをAWSに移行するための巨大な物理ディスクである。ペタバイトスケールのデータ転送ソリューションだ。Snowballのような大きなディスクを使うことで、ネットワークコストの高さ、転送時間の長さ、セキュリティ上の懸念など、一般的な大規模データ転送の問題を回避することができる。スノーボールは設計上非常に安全で、データ転送が完了すると、スノーボールからデータが消去されます。

### Snowball の主な詳細：
- テラバイトから何ペタバイトものデータをAWSに安全かつ迅速に転送する必要がある場合、Snowballはデータ転送の強力な選択肢となります。
- また、既存のネットワーク・インフラに高価なアップグレードをしたくない場合、データの大きなバックログが頻繁に発生する場合、物理的に隔離された環境にある場合、高速インターネット接続が利用できない、またはコスト的に不可能な地域にある場合にも、Snowballは適切な選択肢となります。
- 経験則として、既存のインターネット接続の空き容量を使用してAWSにデータをアップロードするのに1週間以上かかる場合は、Snowballの使用を検討する必要があります。
- 例えば、データ転送専用に使える100Mbの接続があり、合計100TBのデータを転送する必要がある場合、その接続で転送が完了するまで100日以上かかることになる。複数のSnowballを使用すれば、同じ転送を約1週間で行うことができます。
- 以下は、インターネット接続で同じ転送を行うのにかかる日数に基づいて、Snowballを検討すべき場合の参考例です：
- 
![Screen Shot 2020-06-07 at 10 53 22 PM](https://user-images.githubusercontent.com/13093517/83988618-c271d680-a911-11ea-9594-a82f690a786b.png)

### Snowball EdgeとSnowmobile：
- Snowball Edgeは、AWS Lambdaと特定のEC2インスタンスタイプを経由して、コンピュート*と*ストレージ機能の両方が付属しているSnowballの特定のタイプです。これは、データがAmazonデータセンターに送られる途中で、Snowball内でコードを実行できることを意味する。これにより、遠隔地やオフラインの場所でのローカル・ワークロードのサポートが可能になり、その結果、Snowball Edgeはデータ転送サービスに限定される必要がなくなる。興味深いユースケースは旅客機だ。飛行機にはスノーボール・エッジが搭載されていることがあり、大量のフライトデータを保存したり、飛行機自身のシステムに必要な機能を計算したりすることができる。スノーボール・エッジをローカルにクラスタ化することで、パフォーマンスをさらに向上させることもできる。
- スノーモービルはエクサバイト規模のデータ転送ソリューションです。これは100ペタバイトのデータに対応するデータ転送ソリューションで、セミトラックで運ばれる45フィートの輸送コンテナ内に収められている。数年分のデータを含むデータセンター全体をクラウドに移行したい場合、この大規模な転送は理にかなっている。
![image](https://github.com/jTakasuRyuji/AWS-SAA-C02-Study-Guide-JA/assets/8042749/c91b22df-cb5e-4d04-8fc9-7d1099f68638)

## Storage Gateway

### Storage Gateway の概要:
Storage Gatewayは、オンプレミス環境とクラウドベースのストレージを接続し、オンプレミスのアプリケーションとクラウドストレージのバックエンドをシームレスかつ安全に統合するサービスである。Storage Gatewayには3つの種類がある： File Gateway、Volume Gateway、Tape Gatewayである。


### ストレージ・ゲートウェイの詳細
- Storage Gatewayサービスは、物理デバイスか、オンプレミ・データセンターのホストにダウンロードされたVMイメージのどちらかになる。AWSからデータを送受信するためのブリッジとして機能する。
- Storage Gatewayは、LinuxマシンではVMWareのESXiハイパーバイザー、WindowsマシンではMicrosoftのHyper-Vハイパーバイザーの上に置くことができる。
- Storage Gatewayには以下の3種類がある：
  - ファイル・ゲートウェイ（File Gateway）** - NFSまたはSMB経由で動作し、提供される仮想マシン内のネットワーク・ファイルシステム・マウント・ポイントを介してS3にファイルを格納するために使用される。簡単に言えば、File GatewayはS3上のファイルシステムマウントと考えることができる。
  - Volume Gateway** - iSCSI経由で動作し、ハードディスクドライブまたは仮想ハードディスクドライブのコピーをS3に保存するために使用される。これらは*Stored Volumes*または*Cached Volumes*を介して実現できる。簡単に言えば、Volume Gatewayは仮想ハードディスクドライブをクラウドに保存する方法と考えることができる。
  - テープ・ゲートウェイ** - 仮想テープ・ライブラリとして動作する。
- ファイルの所有者、パーミッション、タイムスタンプなど、Storage Gatewayを通過する関連ファイル情報は、それらが属するオブジェクトのメタデータとして保存される。これらのファイル詳細がS3に保存されると、ネイティブに管理できるようになる。つまり、バージョニング、ライフサイクル管理、バケットポリシー、クロスリージョンレプリケーションなど、S3のすべての機能をStorage Gatewayの一部として適用できる。
- ボリューム・ゲートウェイを介したAWSとのアプリケーション・インターフェースは、iSCSIブロック・プロトコルで行われる。これらのボリュームに書き込まれたデータは、ボリュームのコンテンツのポイントインタイムスナップショットとしてAWS Elastic Block Store（EBS）に非同期でバックアップできる。この種のスナップショットは、Gitにおけるプルリクエストと同様に、変更された状態のみをキャプチャする増分バックアップとして機能する。さらに、すべてのスナップショットはストレージ・コストを削減するために圧縮される。
- Tape Gatewayは、テープ（旧式のデータストレージ）を取り除きながら、S3にデータをアーカイブし、レプリケートする耐久性があり、費用対効果の高い方法を提供する。仮想テープライブラリ（VTL）は、既存のテープベースのバックアップインフラを活用し、Tape Gateway上で作成した仮想テープカートリッジにデータを保存する。バックアップを近代化し、クラウドに移行する素晴らしい方法だ。

### ストアドボリュームとキャッシュボリュームの比較：
- Volume Gatewayの**Stored Volumes**では、データをオンプレミスのローカルに保存し、セカンダリデータソースとしてAWSにバックアップすることができます。Stored Volumesは、データセット全体への低レイテンシーアクセスを可能にすると同時に、ハイブリッドクラウドソリューション上での高可用性を提供します。さらに、Stored VolumesをiSCSIドライブとしてアプリケーションインフラにマウントすることができるので、これらのボリュームにデータが書き込まれると、データはオンプレミスのハードウェアに書き込まれ、AWS EBSまたはS3にスナップショットとして非同期にバックアップされる。
  - 以下のStored Volumeアーキテクチャの図では、データはデータセンター内のStorage Area Network、Network Attached、またはDirect Attached Storageからユーザーに提供される。S3は安全で信頼できるバックアップとして存在する。
  - ![Screen Shot 2020-06-08 at 5 10 33 PM](https://user-images.githubusercontent.com/13093517/84080932-05cc5380-a9ab-11ea-8dd5-a80717b1b067.png)

- Volume Gatewayの**Cached Volumes**は、Stored Volumesのようにデータセット全体をローカルに保存しない点が異なる。その代わり、AWSをプライマリー・データ・ソースとして使用し、ローカルのハードウェアをキャッシュ・レイヤーとして使用する。最も頻繁に使用されるコンポーネントのみがオンプレミスのインフラ上に保持され、残りのデータはAWSから提供される。これにより、オンプレミスのインフラを拡張する必要性を最小限に抑えつつ、最も参照されるデータへの低レイテンシーアクセスを維持することができる。
  - 以下のCached Volumeアーキテクチャの図では、最も頻繁にアクセスされるデータは、データセンター内のStorage Area Network、Network Attached、またはDirect Attached Storageからユーザーに提供される。S3はAWSから残りのデータを提供する。
  - ![Screen Shot 2020-06-08 at 5 17 02 PM](https://user-images.githubusercontent.com/13093517/84081406-e5e95f80-a9ab-11ea-82d2-8bd1a53876ba.png)


## Elastic Compute Cloud (EC2)

### EC2 の概要:
EC2はサイズ変更可能なサーバーインスタンスをスピンアップし、素早くスケールアップ/ダウンできる。インスタンスとは、クラウド上の仮想サーバーのことだ。Amazon EC2では、インスタンス上で実行されるオペレーティングシステムとアプリケーションを設定・構成できる。起動時の構成は、インスタンスの起動時に指定した*Amazon Machine Image（AMI）*のライブコピーです。EC2では、新しいインスタンスのプロビジョニングと起動にかかる時間が非常に短縮されており、EC2では、使用した分だけ支払い、使用量が増えるほど支払いが減り、容量を予約するとさらに支払いが減るようになっている。EC2インスタンスが稼働しているときは、CPU、メモリ、ストレージ、ネットワークに課金される。停止中は、EBSストレージに対してのみ課金される。

### EC2 の詳細:
- 単一のAMIから異なるタイプのインスタンスを起動できる。インスタンスタイプは基本的に、インスタンスに使用するホストコンピュータのハードウェアを決定します。各インスタンスタイプは、異なる計算能力とメモリ能力を提供します。インスタンス上で実行する予定のアプリケーションやソフトウェアに必要なメモリ量と計算能力に基づいてインスタンスタイプを選択する必要があります。  
- 次の図に示すように、AMIの複数のインスタンスを起動できます：

![architecture_ami_instance](https://user-images.githubusercontent.com/13093517/84097031-64a4c380-a9d1-11ea-8358-1c3eec1c4471.png)

- インスタンスに専用テナントを使用するオプションがあります。これは、AWSデータセンター内で、物理的なハードウェアに独占的にアクセスできることを意味する。当然、このオプションには高いコストがかかるが、厳格なライセンスポリシーを持つテクノロジーを扱う場合には理にかなっている。
- EC2 VM Importでは、VMware ESX、VMware Workstation、Microsoft Hyper-V、またはCitrix Xenの仮想化フォーマットを使用しているホストであれば、既存のVMをAWSにインポートできる。
- 新しいEC2インスタンスを起動すると、EC2はすべてのVMが異なるハードウェアに分散するようにインスタンスを配置し、障害が1カ所にとどまるようにする。配置グループを使用すると、ワークロードのニーズを満たす相互依存のインスタンスグループの配置に影響を与えることができる。プレースメントグループについては、以下のセクションで説明します。
- Amazon EC2でインスタンスを起動する際、インスタンスの起動時にインスタンスにユーザーデータを渡すオプションがある。このユーザーデータは、一般的な自動設定タスクやスクリプトを実行するために使用できる。たとえば、htopが新しいEC2ホストにインストールされ、常にアクティブであることを確認するbashスクリプトを渡すことができる。
- デフォルトでは、EC2インスタンスのパブリックIPアドレスは、インスタンスが一時的に停止していても、停止時に解放される。そのため、インスタンスは外部DNSホスト名で参照するのがベストである。同じインスタンスに関連付けられる永続的なパブリックIPアドレスが必要な場合は、代わりに基本的に静的IPアドレスであるElastic IPアドレスを使用する。
- SQLデータベースを自己管理する必要がある場合、EC2はRDSの代替となる。高可用性を確保するには、少なくとも1台のEC2インスタンスを別のアベイラビリティゾーンに置くことを忘れないこと。
- ゴールデンイメージとは、必要なソフトウェア／データ／設定の詳細をすべて設定し、すぐに使えるように完全にカスタマイズしたAMIのことだ。この個人用AMIは、新しいインスタンスを起動する際のソースとなります。
- インスタンスのステータスチェックは実行中のEC2サーバーの健全性をチェックし、システムのステータスチェックは基盤となるハイパーバイザーの健全性を監視する。システムステータスの問題に気づいたら、インスタンスを停止し、VMが新しいハイパーバイザー上で再び起動するので、インスタンスを再度起動するだけでよい（再起動は不要）。

### EC2インスタンスの価格：
- オンデマンドインスタンス**は、時間または秒単位の固定料金に基づいています。その名の通り、必要なときにオンデマンドインスタンスを開始し、不要になったら停止することができます。長期的なコミットメントは必要ありません。
- リザーブドインスタンス**では、1年または3年の契約期間でインスタンスを独占的に使用できます。長期のコミットメントにより、1時間単位で大幅な割引が適用されます。
- スポット・インスタンス**は、アマゾンの余剰キャパシティを活用し、興味深い方法で動作します。スポット・インスタンスを利用するには、金銭的に入札する必要があります。スポット・インスタンスはアマゾンのキャパシティが余っている時にのみ利用できるため、このオプションはアプリの開始時間と終了時間がフレキシブルな場合にのみ意味がある。価格変更（例えば、誰かがアクセスに対してより高い価格を入札した）によってインスタンスが停止し、その結果ワークロードが完了しなかった場合でも、課金されることはありません。ただし、インスタンスを自分で終了させた場合は、インスタンスが稼働した時間に対して課金されます。スポット・インスタンスは通常、バッチ処理ジョブで使用されます。

### 標準リザーブドインスタンスとコンバーチブルリザーブドインスタンスとスケジュールリザーブドインスタンス：
- 標準リザーブドインスタンス**は、オンデマンドインスタンスの75%割引となる柔軟性のない予約です。標準リザーブドインスタンスはリージョン間で移動できません。リザーブドインスタンスは、特定のアベイラビリティゾーンまたはリージョン全体に適用するかどうかを選択できますが、リージョンを変更することはできません。
- コンバーチブル・リザーブド・インスタンス**は、オンデマンド・インスタンスの54%割引で提供されるインスタンスです。例えば、数カ月後にVMを汎用型からメモリ最適型に変更する必要があるかもしれないが、まだ確信が持てないとします。そのため、将来的にVMのタイプを変更したり、VMの容量をアップグレードする必要があると考えられる場合は、コンバーチブル・リザーブド・インスタンスを選択してください。ただし、このオプションではインスタンス・タイプのダウングレードはできません。
- スケジュール予約インスタンス**は、設定したタイムラインに従って予約されます。たとえば、学校の授業時間中だけ利用可能である必要がある教育ソフトウェアを実行する場合、スケジュール予約インスタンスを使用することができます。このオプションを使用すると、必要な容量と定期的なスケジュールをより適切に一致させることができるため、コストを節約できます。


### EC2インスタンスのライフサイクル：
次の表は、VMがある時点で取り得る多くのインスタンス状態を示している。

| Instance state | Description | Billing |
| ------------- | ------------- |--------------|
| `pending` | インスタンスは `running` 状態に入る準備をしている。インスタンスが保留状態になるのは、初めて起動するときか、`stopped`状態の後に起動するときです。  | 未請求 |
| `running`  | インスタンスは実行中であり、使用可能である。 | 課金対象 |
| `stopping`  | インスタンスは停止または停止ハイバーネートの準備中です。 | 停止準備中の場合は課金されません。ハイバネート準備中の場合は課金されます。 |
| `stopped` | インスタンスはシャットダウンされ、使用できなくなる。インスタンスはいつでも起動できます。| 課金されない |
| `shutting-down`  | インスタンスは終了準備中です。 | 課金されない |
| `terminated`  | インスタンスは永久に削除され、開始できません。 | 未請求 |

**注***： 注意: 終了されたリザーブドインスタンスは、その期間が終了するまで課金されます。 
 
### EC2 Security:
- Amazon EC2インスタンスをデプロイすると、ゲストオペレーティングシステム（アップデートやセキュリティパッチを含む）、インスタンスにインストールされたアプリケーションソフトウェアやユーティリティ、各インスタンス上のAWS提供のファイアウォール（セキュリティグループと呼ばれる）の設定を管理する責任があります。
- EC2では、インスタンスの終了保護はデフォルトで無効になっている。これは、誤ってインスタンスを終了させないためのセーフガードがないことを意味する。追加の保護が必要な場合は、この機能をオンにする必要がある。
- Amazon EC2は、ログイン情報の暗号化と復号化に公開鍵暗号を使用する。公開鍵暗号方式では、公開鍵を使用してパスワードなどのデータの一部を暗号化し、受信者は秘密鍵を使用してデータを復号化します。公開鍵と秘密鍵は鍵ペアとして知られています。
- OSをインストールするルート・デバイス・ボリュームを暗号化することができます。これはインスタンスの作成時に行うか、ビットロッカーのようなサードパーティツールで行うことができます。もちろん、追加ボリュームやセカンダリEBSボリュームも暗号化できる。


### EC2 Placement Groups:
-  Placement groups balance the tradeoff between risk tolerance and network performance when it comes to your fleet of EC2 instances. The more you care about risk, the more isolated you want your instances to be from each other. The more you care about performance, the more conjoined you want your instances to be with each other. 
- There are three different types of EC2 placement groups:

  1.) Clustered Placement Groups
    - Clustered Placement Grouping is when you put all of your EC2 instances in a single availability zone. This is recommended for applications that need the lowest latency possible and require the highest network throughput.
    - Only certain instances can be launched into this group (compute optimized, GPU optimized, storage optimized, and memory optimized).
  
  2.) Spread Placement Groups
    - Spread Placement Grouping is when you put each individual EC2 instance on top of its own distinct hardware so that failure is isolated. 
    - Your VMs live on separate racks, with separate network inputs and separate power requirements. Spread placement groups are recommended for applications that have a small number of critical instances that should be kept separate from each other. 
  
  3.) Partitioned Placement Groups
    - Partitioned Placement Grouping is similar to Spread placement grouping, but differs because you can have multiple EC2 instances within a single partition. Failure instead is isolated to a partition (say 3 or 4 instances instead of 1), yet you enjoy the benefits of close proximity for improved network performance.
    - With this placement group, you have multiple instances living together on the same hardware inside of different availability zones across one or more regions.
    - If you would like a balance of risk tolerance and network performance, use Partitioned Placement Groups.
  
- Each placement group name within your AWS must be unique
- You can move an existing instance into a placement group provided that it is in a stopped state. You can move the instance via the CLI or an AWS SDK, but not the console. You can also take a snapshot of the existing instance, convert it into an AMI, and launch it into the placement group where you desire it to be.

## Elastic Block Store (EBS)

### EBS の概要:
Amazon EBSボリュームは、1つのEC2インスタンスにアタッチできる耐久性のあるブロックレベルのストレージデバイスだ。EBSはクラウドベースの仮想ハードディスクと考えることができる。EBSボリュームは、インスタンスのシステムドライブやデータベースアプリケーションのストレージなど、頻繁に更新が必要なデータのプライマリストレージとして使用できる。また、継続的なディスクスキャンを行うスループット重視のアプリケーションにも使用できる。

### EBS の詳細:
- EBS volumes persist independently from the running life of an EC2 instance.
- Each EBS volume is automatically replicated within its Availability Zone to protect from both component failure and disaster recovery (similar to Standard S3).
- There are five different types of EBS Storage:
  - General Purpose (SSD)
  - Provisioned IOPS (SSD, built for speed)
  - Throughput Optimized Hard Disk Drive (magnetic, built for larger data loads)
  - Cold Hard Disk Drive (magnetic, built for less frequently accessed workloads)
  - Magnetic
- EBS Volumes offer 99.999% SLA.
- Wherever your EC2 instance is, your volume for it is going to be in the same availability zone
- An EBS volume can only be attached to one EC2 instance at a time.
- After you create a volume, you can attach it to any EC2 instance in the same availability zone.
- Amazon EBS provides the ability to create snapshots (backups) of any EBS volume and write a copy of the data in the volume to S3, where it is stored redundantly in multiple Availability Zones
- An EBS snapshot reflects the contents of the volume during a concrete instant in time.
- An image (AMI) is the same thing, but includes an operating system and a boot loader so it can be used to boot an instance. 
- AMIs can also be thought of as pre-baked, launchable servers. AMIs are always used when launching an instance. 
- When you provision an EC2 instance, an AMI is actually the first thing you are asked to specify. You can choose a pre-made AMI or choose your own made from an EBS snapshot.
- You can also use the following criteria to help pick your AMI:
  - Operating System
  - Architecture (32-bit or 64-bit)
  - Region
  - Launch permissions
  - Root Device Storage (more in the relevant section below)
- You can copy AMIs into entirely new regions.
- When copying AMIs to new regions, Amazon won’t copy launch permissions, user-defined tags, or Amazon S3 bucket permissions from the source AMI to the new AMI. You must ensure those details are properly set for the instances in the new region.
- You can change EBS volumes on the fly, including the size and storage type

### SSD vs. HDD:
- SSD-backed volumes are built for transactional workloads involving frequent read/write operations, where the dominant performance attribute is IOPS. **Rule of thumb**: Will your workload be IOPS heavy? Plan for SSD.
- HDD-backed volumes are built for large streaming workloads where throughput (measured in MiB/s) is a better performance measure than IOPS. **Rule of thumb**: Will your workload be throughput heavy? Plan for HDD.

![hdd_vs_ssd](https://user-images.githubusercontent.com/13093517/84944872-76165b80-b0b4-11ea-819c-a93deb999ea2.png)


### EBS Snapshots:
- EBS Snapshots are point in time copies of volumes. You can think of Snapshots as photographs of the disk’s current state and the state of everything within it.
- A snapshot is constrained to the region where it was created.
- Snapshots only capture the state of change from when the last snapshot was taken. This is what is recorded in each new snapshot, not the entire state of the server.
- Because of this, it may take some time for your first snapshot to be created. This is because the very first snapshot's change of state is the entire new volume. Only afterwards will the delta be captured because there will then be something previous to compare against. 
- EBS snapshots occur asynchronously which means that a volume can be used as normal while a snapshot is taking place.
- When creating a snapshot for a future root device, it is considered best practices to stop the running instance where the original device is before taking the snapshot.
- The easiest way to move an EC2 instance and a volume to another availability zone is to take a snapshot.
- When creating an image from a snapshot, if you want to deploy a different volume type for the new image (e.g. General Purpose SSD -> Throughput Optimized HDD) then you must make sure that the virtualization for the new image is hardware-assisted.
- A short summary for creating copies of EC2 instances: Old instance -> Snapshot -> Image (AMI) -> New instance
- You cannot delete a snapshot of an EBS Volume that is used as the root device of a registered AMI. If the original snapshot was deleted, then the AMI would not be able to use it as the basis to create new instances. For this reason, AWS protects you from accidentally deleting the EBS Snapshot, since it could be critical to your systems. To delete an EBS Snapshot attached to a registered AMI, first remove the AMI, then the snapshot can be deleted.



### EBS Root Device Storage:
- All AMI root volumes (where the EC2's OS is installed) are of two types: EBS-backed or Instance Store-backed
- When you delete an EC2 instance that was using an Instance Store-backed root volume, your root volume will also be deleted. Any additional or secondary volumes will persist however.
- If you use an EBS-backed root volume, the root volume will not be terminated with its EC2 instance when the instance is brought offline. EBS-backed volumes are not temporary storage devices like Instance Store-backed volumes.
- EBS-backed Volumes are launched from an AWS EBS snapshot, as the name implies
- Instance Store-backed Volumes are launched from an AWS S3 stored template. They are ephemeral, so be careful when shutting down an instance!
- Secondary instance stores for an instance-store backed root device must be installed during the original provisioning of the server. You cannot add more after the fact. However, you can add EBS volumes to the same instance after the server's creation.
- With these drawbacks of Instance Store volumes, why pick one? Because they have a very high IOPS rate. So while an Instance Store can't provide data persistence, it can provide much higher IOPS compared to network attached storage like EBS. 
- Further, Instance stores are ideal for temporary storage of information that changes frequently such as buffers, caches, scratch data, and other temporary content, or for data that is replicated across a fleet of instances, such as a load-balanced pool of web servers.
- When to use one over the other?
  - Use EBS for DB data, critical logs, and application configs.
  - Use instance storage for in-process data, noncritical logs, and transient application state.
  - Use S3 for data shared between systems like input datasets and processed results, or for static data needed by each new system when launched.

### EBS Encryption:
- EBS encryption offers a straight-forward encryption solution for EBS resources that doesn't require you to build, maintain, and secure your own key management infrastructure.
- It uses AWS Key Management Service (AWS KMS) customer master keys (CMK) when creating encrypted volumes and snapshots. 
- You can encrypt both the root device and secondary volumes of an EC2 instance. When you create an encrypted EBS volume and attach it to a supported instance type, the following types of data are encrypted:
  - Data at rest inside the volume
  - All data moving between the volume and the instance
  - All snapshots created from the volume
  - All volumes created from those snapshots
- EBS encrypts your volume with a data key using the AES-256 algorithm. 
- Snapshots of encrypted volumes are naturally encrypted as well. Volumes restored from encrypted snapshots are also encrypted. You can only share unencrypted snapshots.
- The old way of encrypting a root device was to create a snapshot of a provisioned EC2 instance. While making a copy of that snapshot, you then enabled encryption during the copy's creation. Finally, once the copy was encrypted, you then created an AMI from the encrypted copy and used to have an EC2 instance with encryption on the root device. Because of how complex this is, you can now simply encrypt root devices as part of the EC2 provisioning options.

## Elastic Network Interfaces (ENI)

### ENI の概要:
エラスティック・ネットワーク・インターフェースは、仮想ネットワークカードを表すネットワーキングコンポーネントです。新しいインスタンスをプロビジョニングすると、ENIが自動的にアタッチされます。あるインスタンスから別のインスタンスにネットワーク・インターフェイスを移動すると、ネットワーク・トラフィックは新しいインスタンスにリダイレクトされます。

### ENI の詳細:
- ENI is used mainly for low-budget, high-availability network solutions
- However, if you suspect you need high network throughput then you can use Enhanced Networking ENI.
- Enhanced Networking ENI uses single root I/O virtualization to provide high-performance networking capabilities on supported instance types. SR-IOV provides higher I/O and lower throughput and it ensures higher bandwidth, higher packet per second (PPS) performance, and consistently lower inter-instance latencies. SR-IOV does this by dedicating the interface to a single instance and effectively bypassing parts of the Hypervisor which allows for better performance.
- Adding more ENIs won’t necessarily speed up your network throughput, but Enhanced Networking ENI will.
- There is no extra charge for using Enhanced Networking ENI and the better network performance it provides. The only downside is that Enhanced Networking ENI is not available on all EC2 instance families and types.
- You can attach a network interface to an EC2 instance in the following ways:
  - When it's running (hot attach)
  - When it's stopped (warm attach)
  - When the instance is being launched (cold attach).
- If an EC2 instance fails with ENI properly configured, you (or more likely,the code running on your behalf) can attach the network interface to a hot standby instance. Because ENI interfaces maintain their own private IP addresses, Elastic IP addresses, and MAC address, network traffic will begin to flow to the standby instance as soon as you attach the network interface on the replacement instance. Users will experience a brief loss of connectivity between the time the instance fails and the time that the network interface is attached to the standby instance, but no changes to the VPC route table or your DNS server are required.
- For instances that work with Machine Learning and High Performance Computing, use EFA (Elastic Fabric Adaptor). EFAs accelerate the work required from the above use cases. EFA provides lower and more consistent latency and higher throughput than the TCP transport traditionally used in cloud-based High Performance Computing systems. 
- EFA can also use OS-bypass (on linux only) that will enable ML and HPC applications to interface with the Elastic Fabric Adaptor directly, rather than be normally routed to it through the OS. This gives it a huge performance increase.
- You can enable a VPC flow log on your network interface to capture information about the IP traffic going to and from a network interface. 

## Security Groups

### Security Groups の概要:
セキュリティグループは、EC2でのアクセス（SSH、HTTP、RDPなど）を制御するために使用される。セキュリティグループはインスタンスの仮想ファイアウォールとして機能し、インバウンドとアウトバウンドのトラフィックを制御する。VPCでインスタンスを起動する際、最大5つのセキュリティグループをインスタンスに割り当てることができ、セキュリティグループはサブネットレベルではなくインスタンスレベルで機能する。

### Security Groups の詳細:
- Security groups control inbound and outbound traffic for your instances (they act as a Firewall for EC2 Instances) while NACLs control inbound and outbound traffic for your subnets (they act as a Firewall for Subnets). Security Groups usually control the list of ports that are allowed to be used by your EC2 instances and the NACLs control which network or list of IP addresses can connect to your whole VPC.
- Every time you make a change to a security group, that change occurs immediately
- Whenever you create an inbound rule, an outbound rule is created immediately. This is because Security Groups are *stateful*. This means that when you create an ingress rule for a security group, a corresponding egress rule is created to match it. This is in contrast with NACLs which are *stateless* and require manual intervention for creating both inbound and outbound rules.
- Security Group rules are based on ALLOWs and there is no concept of DENY when in comes to Security Groups. This means you cannot explicitly deny or blacklist specific ports via Security Groups, you can only implicitly deny them by excluding them in your ALLOWs list
- Because of the above detail, everything is blocked by default. You must go in and intentionally allow access for certain ports. 
- Security groups are specific to a single VPC, so you can't share a Security Group between multiple VPCs. However, you can copy a Security Group to create a new Security Group with the same rules in another VPC for the same AWS Account.
- Security Groups are regional and can span AZs, but can't be cross-regional.
- Outbound rules exist if you need to connect your server to a different service such as an API endpoint or a DB backend. You need to enable the ALLOW rule for the correct port though so that traffic can leave EC2 and enter the other AWS service.
- You can attach multiple security groups to one EC2 instance and you can have multiple EC2 instances under the umbrella of one security group
- You can specify the source of your security group (basically who is allowed to bypass the virtual firewall) to be a single **/32** IP address, an IP range, or even a separate security group.
- You cannot block specific IP addresses with Security Groups (use NACLs instead)
- You can increase your Security Group limit by submitting a request to AWS

## Web Application Firewall (WAF)

### WAF の概要:
AWS WAFは、CloudFront、API Gateway、Application Load Balancers、EC2、およびその他のレイヤー7からAWS環境へのHTTPリクエストを許可またはブロックするWebアプリケーションです。AWS WAFは、SQLインジェクションやクロスサイトスクリプティングなどの一般的な攻撃パターンをブロックするセキュリティルールや、定義した特定のトラフィックパターンをフィルタリングするルールを作成できるため、トラフィックがアプリケーションに到達する方法を制御できる。WAFのデフォルトのルールセットは、OWASPトップ10のセキュリティリスクのような問題に対処し、新しい脆弱性が発見されるたびに定期的に更新されます。

### WAF の詳細:
- As mentioned above, WAF operates as a Layer 7 firewall. This grants it the ability to monitor granular web-based conditions like URL query string parameters. This level of detail helps to detect both foul play and honest issues with the requests getting passed onto your AWS environment.
- With WAF, you can set conditions such as which IP addresses are allowed to make what kind of requests or access what kind of content.
- Based off of these conditions, the corresponding endpoint will either allow the request by serving the requested content or return an HTTP 403 Forbidden status.
- At the simplest level, AWS WAF lets you choose one of the following behaviors:
  - **Allow all requests except the ones that you specify**: This is useful when you want CloudFront or an Application Load Balancer to serve content for a public website, but you also want to block requests from attackers.
  - **Block all requests except the ones that you specify**: This is useful when you want to serve content for a restricted website whose users are readily identifiable by properties in web requests, such as the IP addresses that they use to browse to the website.
  - **Count the requests that match the properties that you specify**: When you want to allow or block requests based on new properties in web requests, you first can configure AWS WAF to count the requests that match those properties without allowing or blocking those requests. This lets you confirm that you didn't accidentally configure AWS WAF to block all the traffic to your website. When you're confident that you specified the correct properties, you can change the behavior to allow or block requests.

### WAF Protection Capabilities:
- The different request characteristics that can be used to limit access:
  - The IP address that a request originates from
  - The country that a request originates from
  - The values found in the request headers
  - Any strings that appear in the request (either specific strings or strings that match a regex pattern)
  - The length of the request
  - Any presence of SQL code (likely a SQL injection attempt)
  - Any presence of a script (likely a cross-site scripting attempt)
- You can also use NACLs to block malicious IP addresses, prevent SQL injections / XSS, and block requests from specific countries. However, it is good form to practice defense in depth. 
- Denying or blocking malicious users at the WAF level has the added advantage of protecting your AWS ecosystem at its outermost border.

## CloudWatch

### CloudWatch の概要:
Amazon CloudWatchはモニタリングと監視のサービスです。アプリケーションを監視し、システム全体のパフォーマンス変化に対応し、リソース利用を最適化し、運用の健全性を統一的に把握するためのデータと実用的な洞察を提供します。

### CloudWatch の詳細:
- CloudWatch collects monitoring and operational data in the form of logs, metrics, and events.
- You can use CloudWatch to detect anomalous behavior in your environments, set alarms, visualize logs and metrics side by side, take automated actions, troubleshoot issues, and discover insights to keep your applications
running smoothly.
- Within the compute domain, CloudWatch can inform you about the health of EC2 instances, Autoscaling Groups, Elastic Load Balancers, and Route53 Health Checks.
Within the storage and content delivery domains, CloudWatch can inform you about the health of EBS Volumes, Storage Gateways, and CloudFront.
- With regards to EC2, CloudWatch can only monitor host level metrics such as CPU, network, disk, and status checks for insights like the health of the underlying hypervisor.
- CloudWatch is *NOT* CloudTrail so it is important to know that only CloudTrail can monitor AWS access for security and auditing reasons. CloudWatch is all about performance. CloudTrail is all about auditing.
- CloudWatch with EC2 will monitor events every 5 minutes by default, but you can have 1 minute intervals if you use Detailed Monitoring.

![Screen Shot 2020-06-17 at 8 16 23 PM](https://user-images.githubusercontent.com/13093517/84963455-71af6a00-b0d7-11ea-8168-15dd791bf000.png)

- You can customize your CloudWatch dashboards for insights.
- There is a multi-platform CloudWatch agent which can be installed on both Linux and Windows-based instances. This agent enables you to select the metrics to be collected, including sub-resource metrics such as per-CPU core. You can use this single agent to collect both system metrics and log files from Amazon EC2 instances and on-premises servers.
- The following metrics are not collected from EC2 instances via CloudWatch:
  - Memory utilization
  - Disk swap utilization
  - Disk space utilization
  - Page file utilization
  - Log collection
- If you need the above information, then you can retrieve it via the official CloudWatch agent or you can create a custom metric and send the data on your own via a custom script.
- CloudWatch's key purpose:
  - Collect metrics
  - Collect logs
  - Collect events
  - Create alarms
  - Create dashboards

### CloudWatch Logs:
- Amazon CloudWatch Logsを使って、Amazon EC2インスタンス、AWS CloudTrail、Amazon Route 53、その他のソースからのログファイルを監視、保存、アクセスすることができる。そして、CloudWatch Logsから関連するログデータを取得することができる。
- CloudWatch Logsは、使用するすべてのシステム、アプリケーション、AWSサービスからのログを、単一の拡張性の高いサービスに一元化するのに役立つ。
- ロググループを作成し、CloudWatch Logsの論理ユニットを結合することができる。
- カスタム・ログ・ファイルをストリーミングして、さらなる洞察を得ることができます。

### CloudWatch Events:
- Amazon CloudWatch Events delivers a near real-time stream of system events that describe changes in AWS resources. 
- You can use events to trigger lambdas for example while using alarms to inform you that something went wrong.

### CloudWatch Alarms:
- CloudWatch alarms send notifications or automatically make changes to the resources you are monitoring based on rules that you define. 
- For example, you can create custom CloudWatch alarms which will trigger notifications such as surpassing a set billing threshold.
- CloudWatch alarms have two states of either `ok` or `alarm`

### CloudWatch Metrics:
- CloudWatch Metrics represent a time-ordered set of data points.
- These basically are a variable you can monitor over time to help tell if everything is okay, e.g. Hourly CPU Utilization.
- CloudWatch Metrics allows you to track high resolution metrics at sub-minute intervals all the way down to per second.

### CloudWatch Dashboards:
- CloudWatchダッシュボードはCloudWatchコンソールのカスタマイズ可能なホームページで、リソースを単一のビューで監視するために使用できます。
- これらのダッシュボードはCloudWatch MetricsやCloudWatch Alarmsと統合され、AWSリソースのメトリクスやアラームのカスタマイズされたビューを作成します。

## CloudTrail

### CloudTrail の概要:
AWS CloudTrailは、AWSアカウントのガバナンス、コンプライアンス、運用監査、リスク監査を可能にするサービスです。CloudTrailを使用することで、AWSインフラストラクチャ全体のアクションに関連するアカウントのアクティビティをログに記録し、継続的に監視し、保持することができます。CloudTrailは、AWS Management Console、AWS SDK、コマンドラインツール、APIコール、その他のAWSサービスを通じて行われたアクションを含む、AWSアカウントのアクティビティのイベント履歴を提供します。これはリージョナルサービスですが、すべてのリージョンで証跡を収集するようにCloudTrailを構成することができます。

### CloudTrail の詳細:
- CloudTrail Events logs API calls or activities. 
- CloudTrail Events stores the last 90 days of events in its Event History. This is enabled by default and is no additional cost.
- This event history simplifies security analysis, resource change tracking, and troubleshooting.
- There are two types of events that can be logged in CloudTrail: management events and data events. 
- Management events provide information about management operations that are performed on resources in your AWS account. 
- Think of Management events as things normally done by people when they are in AWS. Examples:
  - a user sign in
  - a policy changed
  - a newly created security configuration
  - a logging rule deletion
- Data events provide information about the resource operations performed on or in a resource. 
- Think of Data events as things normally done by software when hitting various AWS endpoints. Examples:
  - S3 object-level API activity
  - Lambda function execution activity 
- By default, CloudTrail logs management events, but not data events. 
- By default, CloudTrail Events log files are encrypted using Amazon S3 server-side encryption (SSE). You can also choose to encrypt your log files with an AWS Key Management Service (AWS KMS) key. As these logs are stored in S3, you can define Amazon S3 lifecycle rules to archive or delete log files automatically. If you want notifications about log file delivery and validation, you can set up Amazon SNS notifications.

## Elastic File System (EFS)

### EFS の概要:
EFSは、AWS内で使用するためのシンプルで完全に管理されたエラスティックNFSファイルシステムを提供します。EFSは、アプリケーションを中断することなく、ファイルの追加や削除に応じてファイルシステムのストレージ容量を自動的かつ瞬時に増減します。

### EFS の詳細:
- In EFS, storage capacity is elastic (grows and shrinks automatically) and its size changes based on adding or removing files.
- While EBS mounts one EBS volume to one instance, you can attach one EFS volume across multiple EC2 instances.
- The EC2 instances communicate to the remote file system using the NFSv4 protocol. This makes it required to open up the NFS port for our security group (EC2 firewall rules) to allow inbound traffic on that port.
- Within an EFS volume, the mount target state will let you know what instances are available for mounting
- With EFS, you only pay for the storage that you use so you pay as you go. No pre-provisioning required.
- EFS can scale up to the petabytes and can support thousands of concurrent NFS connections.
- Data is stored across multiple AZs in a region and EFS ensures read after write consistency.
- It is best for file storage that is accessed by a fleet of servers rather than just one server

## Amazon FSx for Windows

### Amazon FSx for Windows の概要:
Amazon FSx for Windows File Serverは、完全に管理されたネイティブのMicrosoft File Systemを提供します。

### Amazon FSx for Windows の詳細:
- With FSx for Windows, you can easily move your Windows-based applications that require file storage in AWS.
- It is built on Windows Server and exists solely for Microsoft-based applications so if you need SMB-based file storage then choose FSx.
- FSx for Windows also permits connectivity between on-premise servers and AWS so those same on-premise servers can make use of Amazon FSx too.
- You can use Microsoft Active Directory to authenticate into the file system.
- Amazon FSx for Windows provides multiple levels of security and compliance to help ensure your data is protected. Amazon FSx automatically encrypts your data at-rest and in-transit.
- You can access Amazon FSx for Windows from a variety of compute resources, not just EC2.
- You can deploy your Amazon FSx for Windows in a single AZ or in a Multi-AZ configuration.
- You can use SSD or HDD for the storage device depending on your requirements.
- FSx for Windows support daily automated backups and admins in taking backups when needed as well.
- FSx for Windows removes duplicated content and compresses common content
- By default, all data is encrypted at rest.

## Amazon FSx for Lustre

### Amazon FSx for Lustre の概要:
Amazon FSx for Lustreは、ハイパフォーマンス・コンピューティング・アプリケーション向けにオープンソースのLustreファイルシステムを簡単かつコスト効率よく立ち上げ、実行できるようにします。FSx for Lustreを使用すると、最大で毎秒数百ギガバイトのスループット、数百万のIOPS、サブミリ秒のレイテンシで巨大なデータセットを処理できるファイルシステムを立ち上げて実行できます。

### Amazon FSx for Lustre の詳細:
- FSx for Lustre is compatible with the most popular Linux-based AMIs, including Amazon Linux, Amazon Linux 2, Red Hat Enterprise Linux (RHEL), CentOS, SUSE Linux and Ubuntu.
- Since the Lustre file system is designed for high-performance computing workloads that typically run on compute clusters, choose EFS for normal Linux file system if your requirements don't match this use case.
- FSx Lustre has the ability to store and retrieve data directly on S3 on its own.

## Relational Database Service (RDS)

### RDS の概要:
RDSは、AWSにおけるリレーショナルデータベースのセットアップ、運用、スケーリングを容易にするマネージドサービスです。ハードウェアのプロビジョニング、データベースのセットアップ、パッチ適用、バックアップなど、時間のかかる管理作業を自動化またはアウトソーシングしながら、コスト効率に優れたサイズ変更可能なキャパシティを提供します。

### RDS の詳細:
- RDS comes in six different flavors:
  - SQL Server
  - Oracle
  - MySQL Server
  - PostgreSQL
  - MariaDB
  - Aurora
- Think of RDS as the DB engine in which various DBs sit on top of.
- RDS has two key features when scaling out:
  - Read replication for improved performance
  - Multi-AZ for high availability
- In the database world, *Online Transaction Processing (OLTP)* differs from *Online Analytical Processing (OLAP)* in terms of the type of querying that you would do. OLTP serves up data for business logic that ultimately composes the core functioning of your platform or application. OLAP is to gain insights into the data that you have stored in order to make better strategic decisions as a company.
- RDS runs on virtual machines, but you do not have access to those machines. You cannot SSH into an RDS instance so therefore you cannot patch the OS. This means that AWS  is responsible for the security and maintenance of RDS. You can provision an EC2 instance as a database if you need or want to manage the underlying server yourself, but not with an RDS engine.
- Just because you cannot access the VM directly, it does not mean that RDS is serverless. There is Aurora serverless however (explained below) which serves a niche purpose.
- SQS queues can be used to store pending database writes if your application is struggling under a high write load. These writes can then be added to the database when the database is ready to process them. Adding more IOPS will also help, but this alone will not wholly eliminate the chance of writes being lost. A queue however ensures that writes to the DB do not become lost.


### RDS Multi-AZ:
- Disaster recovery in AWS always looks to ensure standby copies of resources are maintained in a separate geographical area. This way, if a disaster (natural disaster, political conflict, etc.) ever struck where your original resources are, the copies would be unaffected.
- When you provision a Multi-AZ DB Instance, Amazon RDS automatically creates a primary DB instance and synchronously replicates the data to a standby instance in a different Availability Zone (AZ). Each AZ runs on its own physically distinct, independent infrastructure, and is engineered to be highly reliable.
- With a Multi-AZ configuration, EC2 connects to its RDS data store using a DNS address masked as a connection string. If the primary DB fails, Multi-AZ is smart enough to detect that failure and automatically update the DNS address to point at the secondary. No manual intervention is required and AWS takes care of swapping the IP address in DNS.
- Multi-AZ is supported for all DB flavors except aurora. This is because Aurora is completely fault-tolerant on its own.
- Multi-AZ feature allows for high availability across availability zones and not regions.
- During a failover, the recovered former primary becomes the new secondary and the promoted secondary becomes primary. Once the original DB is recovered, there will be a sync process kicked off where the two DBs mirror each other once to sync up on the new data that the failed former primary might have missed out on.
- You can force a failover for a Multi-AZ setup by rebooting the primary instance
- With a Multi-AZ RDS configuration, backups are taken from the standby.


### RDS Read Replicas:
- Read Replication is exclusively used for performance enhancement.
- With a Read Replica configuration, EC2 connects to the RDS backend using a DNS address and every write that is received by the master database is also passed onto a DB secondary so that it becomes a perfect copy of the master. This has the overall effect of reducing the number of transactions on the master because the secondary DBs can be queried for the same data. 
- However, if the master DB were to fail, there is no automatic failover. You would have to manually create a new connection string to sync with one of the read replicas so that it becomes a master on its own. Then you’d have to update your EC2 instances to point at the read replica. You can have up to five copies of your master DB with read replication.
- You can promote read replicas to be their very own production database if needed.
- Read replicas are supported for all six flavors of DB on top of RDS.
- Each Read Replica will have its own DNS endpoint. 
- Automated backups must be enabled in order to use read replicas.
- You can have read replicas with Multi-AZ turned on or have the read replica in an entirely separate region. You can even have read replicas of read replicas, but watch out for latency or replication lag.
The caveat for Read Replicas is that they are subject to small amounts of replication lag. This is because they might be missing some of the latest transactions as they are not updated as quickly as primaries. Application designers need to consider which queries have tolerance to slightly stale data. Those queries should be executed on the read replica, while those demanding completely up-to-date data should run on the primary node.


### RDS Backups:
- When it comes to RDS, there are two kinds of backups:
  - automated backups
  - database snapshots
- **Automated backups** allow you to recover your database to any point in time within a retention period (between one and 35 days). Automated backups will take a full daily snapshot and will also store transaction logs throughout the day. When you perform a DB recovery, RDS will first choose the most recent daily backup and apply the relevant transaction logs from that day. Within the set retention period, this gives you the ability to do a point in time recovery down to the precise second.
Automated backups are enabled by default. The backup data is stored freely up to the size of your actual database (so for every GB saved in RDS, that same amount will freely be stored in S3 up until the GB limit of the DB). Backups are taken within a defined window so latency might go up as storage I/O is suspended in order for the data to be backed up.
- **DB snapshots** are done manually by the administrator. A key different from automated backups is that they are retained even after the original RDS instance is terminated. With automated backups, the backed up data in S3 is wiped clean along with the RDS engine. This is why you are asked if you want to take a final snapshot of your DB when you go to delete it.
- When you go to restore a DB via automated backups or DB snapshots, the result is the provisioning of an entirely new RDS instance with its own DB endpoint in order to be reached.

### RDS Security:
- You can authenticate to your DB instance using IAM database authentication. IAM database authentication works with MySQL and PostgreSQL. With this authentication method, you don't need to use a password when you connect to a DB instance. Instead, you use an authentication token. 
- An authentication token is a unique string that Amazon RDS generates on request. Authentication tokens have a lifetime of 15 minutes. You don't need to store user credentials in the database because authentication is managed externally using IAM.
- IAM database authentication provides the following benefits:
  - Network traffic to and from the database is encrypted using Secure Sockets Layer (SSL).
  - You can use IAM to centrally manage access to your database resources, instead of managing access individually on each DB instance.
  - For applications running on Amazon EC2, you can use profile credentials specific to your EC2 instance to access your database instead of a password, for greater security
- Encryption at rest is supported for all six flavors of DB for RDS. Encryption is done using the AWS KMS service. Once the RDS instance has encryption enabled, the data in the DB becomes encrypted as well as all backups (automated or snapshots) and read replicas.
- After your data is encrypted, Amazon RDS handles authentication of access and decryption of your data transparently with a minimal impact on performance. You don't need to modify your database client applications to use encryption. 
- Amazon RDS encryption is currently available for all database engines and storage types. However, you need to ensure that the underlying instance type supports DB encryption.
- You can only enable encryption for an Amazon RDS DB instance when you create it, not after the DB instance is created and 
DB instances that are encrypted can't be modified to disable encryption. 

### RDS Enhanced Monitoring:
- RDSには拡張モニタリング機能があります。Amazon RDSはDBインスタンスが稼働しているオペレーティングシステム（OS）のメトリクスをリアルタイムで提供します。コンソールを使ってDBインスタンスのメトリクスを表示したり、CloudWatch Logsから出力されたEnhanced MonitoringのJSONを任意のモニタリングシステムで利用することができます。
- デフォルトでは、Enhanced Monitoringのメトリクスは30日間CloudWatch Logsに保存されます。メトリクスがCloudWatch Logsに保存される期間を変更するには、CloudWatchコンソールでRDS OS MetricsロググループのRetentionを変更します。
- CloudWatchとEnhanced Monitoring Metricsには重要な違いがあることに注意してください。CloudWatchはDBインスタンスのハイパーバイザーからCPU使用率のメトリクスを収集し、Enhanced Monitoringはインスタンス上のエージェントからメトリクスを収集します。その結果、ハイパーバイザー層がメトリクスの一部としてピックアップされ解釈される可能性のある少量の作業を実行するため、測定値の間に違いが見つかるかもしれません。

## Aurora

### Aurora の概要:
AuroraはAWSのフラッグシップDBであり、従来のエンタープライズデータベースのパフォーマンスと可用性、オープンソースデータベースのシンプルさと費用対効果を兼ね備えていることで知られている。MySQL/PostgreSQL互換のRDBMSであり、商用データベースのセキュリティ、可用性、信頼性を競合他社の1/10のコストで提供する。MySQLは5倍、PostgreSQLは3倍のパフォーマンス倍率があるため、AWSデータベースとしてはるかに効果的です。

### Aurora の詳細:
- In case of an infrastructure failure, Aurora performs an automatic failover to a replica of its own.
- Amazon Aurora typically involves a cluster of DB instances instead of a single instance. Each connection is handled by a specific DB instance. When you connect to an Aurora cluster, the host name and port that you specify point to an intermediate handler called an endpoint. Aurora uses the endpoint mechanism to abstract these connections. Thus, you don't have to hard code all the host names or write your own logic for load-balancing and rerouting connections when some DB instances aren't available.
- By default, there are 2 copies in a minimum of 3 availability zones for 6 total copies of all of your Aurora data. This makes it possible for it to handle the potential loss of up to 2 copies of your data without impacting write availability and up to 3 copies of your data without impacting read availability.
- Aurora storage is self-healing and data blocks and disks are continuously scanned for errors. If any are found, those errors are repaired automatically.
- Aurora replication differs from RDS replicas in the sense that it is possible for Aurora's replicas to be both a standby as part of a multi-AZ configuration as well as a target for read traffic. In RDS, the multi-AZ standby cannot be configured to be a read endpoint and only read replicas can serve that function.
- With Aurora replication, you can have up to fifteen copies. If you want downstream MySQL or PostgreSQL as you replicated copies, then you can only have 5 or 1.
- Automated failover is only possible with Aurora read replication
- For more on the differences between RDS replication and Aurora Replication, please consult the following:

![Screen Shot 2020-06-18 at 3 02 39 PM](https://user-images.githubusercontent.com/13093517/85061446-d240b480-b174-11ea-9dc4-f40d82743250.png)

- Automated backups are always enabled on Aurora instances and backups don’t impact DB performance. You can also take snapshots which also don’t impact performance. Your snapshots can be shared across AWS accounts.
- A common tactic for migrating RDS DBs into Aurora RDs is to create a read replica of a RDS MariaDB/MySQL DB as an Aurora DB. Then simply promote the Aurora DB into a production instance and delete the old MariaDB/MySQL DB.
- Aurora starts w/ 10GB and scales per 10GB all the way to 128 TB via storage autoscaling. Aurora's computing power scales up to 32vCPUs and 244GB memory

### Aurora Serverless:
- Aurora Serverless is a simple, on-demand, autoscaling configuration for the MySQL/PostgreSQl-compatible editions of Aurora. With Aurora Serverless, your instance automatically scales up or down and starts on or off based on your application usage. The use cases for this service are infrequent, intermittent, and unpredictable workloads.
- This also makes it possible cheaper because you only pay per invocation
- With Aurora Serverless, you simply create a database endpoint, optionally specify the desired database capacity range, and connect your applications. 
- It removes the complexity of managing database instances and capacity. The database will automatically start up, shut down, and scale to match your application's needs. It will seamlessly scale compute and memory capacity as needed, with no disruption to client connections.

### Aurora Cluster Endpoints:
- クラスタエンドポイントを使用すると、各接続をユースケースに基づいて適切なインスタンスまたはインスタンスグループにマッピングします。
- Aurora DB全体で異なるロールまたはジョブに関連付けられたクラスタエンドポイントに接続できます。これは、異なるインスタンスまたはインスタンスグループが異なる機能を実行するためです。
- 例えば、DDL文を実行するにはプライマリインスタンスに接続します。クエリを実行するには、リーダエンドポイントに接続し、Auroraは自動的にリーダエンドポイントの背後にあるすべてのAuroraレプリカ間で負荷分散を実行します。診断やチューニングのために、別のエンドポイントに接続して詳細を調べることができます。
- フェイルオーバー後も DB インスタンスの入口は変わらないので、アプリケーションはどのエンドポイントでも手動で管理介入することなくデータベース操作を再開できます。

### Aurora Reader Endpoints:
- Aurora Reader endpoints are a subset of the above idea of cluster endpoints. Use the reader endpoint for read operations, such as queries. By processing those statements on the read-only Aurora Replicas, this endpoint reduces the overhead on the primary instance. 
- There are up 15 Aurora Read Replicas because a Reader Endpoint to help handle read-only query traffic.
- It also helps the cluster to scale the capacity to handle simultaneous SELECT queries, proportional to the number of Aurora Replicas in the cluster. Each Aurora DB cluster has one reader endpoint.
- If the cluster contains one or more Aurora Replicas, the reader endpoint load-balances each connection request among the Aurora Replicas. In that case, you can only perform read-only statements such as SELECT in that session. If the cluster only contains a primary instance and no Aurora Replicas, the reader endpoint connects to the primary instance directly. In that case, you can perform write operations through the endpoint.

## DynamoDB

### DynamoDB の概要:
Amazon DynamoDBは、あらゆるスケールで1桁ミリ秒のパフォーマンスを実現するキーバリューおよびドキュメントデータベースです。完全に管理され、マルチリージョン、マルチマスター、耐久性のある非SQLデータベースです。セキュリティ、バックアップとリストア、インターネットスケールのアプリケーションのためのインメモリキャッシングが組み込まれています。

### DynamoDB の詳細:
- The main components of DynamoDB are:
  - a collection which serves as the foundational table
  - a document which is equivalent to a row in a SQL database
  - key-value pairs which are the fields within the document or row
- The convenience of non-relational DBs is that each row can look entirely different based on your use case. There doesn't need to be uniformity. For example, if you need a new column for a particular entry you don't also need to ensure that that column exists for the other entries.
- DynamoDB supports both document and key-value based models. It is a great fit for mobile, web, gaming, ad-tech, IoT, etc.
- DynamoDB is stored via SSD which is why it is so fast.
- It is spread across 3 geographically distinct data centers.
- The default consistency model is Eventually Consistent Reads, but there are also Strongly Consistent Reads.
- The difference between the two consistency models is the one second rule. With Eventual Consistent Reads, all copies of data are usually identical within one second after a write operation. A repeated read after a short period of time should return the updated data. However, if you need to read updated data within or less than a second and this needs to be a guarantee, then strongly consistent reads are your best bet.
- If you face a scenario that requires the schema, or the structure of your data, to change frequently, then you have to pick a database which provides a non-rigid and flexible way of adding or removing new types of data. This is a classic example of choosing between a relational database and non-relational (NoSQL) database. In this scenario, pick DynamoDB.
- A relational database system does not scale well for the following reasons:
  - It normalizes data and stores it on multiple tables that require multiple queries to write to disk.
  - It generally incurs the performance costs of an ACID-compliant transaction system.
  - It uses expensive joins to reassemble required views of query results.
- High cardinality is good for DynamoDB I/O performance. The more distinct your partition key values are, the better.  It makes it so that the requests sent will be spread across the partitioned space. 
- DynamoDB makes use of parallel processing to achieve predictable performance. You can visualize each partition or node as an independent DB server of fixed size with each partition or node responsible for a defined block of data. In SQL terminology, this concept is known as sharding but of course DynamoDB is not a SQL-based DB. With DynamoDB, data is stored on Solid State Drives (SSD).

### DynamoDB Accelerator (DAX):
- Amazon DynamoDB Accelerator (DAX) is a fully managed, highly available, in-memory cache that can reduce Amazon DynamoDB response times from milliseconds to microseconds, even at millions of requests per second.
- With DAX, your applications remain fast and responsive, even when unprecedented request volumes come your way. There is no tuning required. 
- DAX lets you scale on-demand out to a ten-node cluster, giving you millions of requests per second.
- DAX does more than just increase read performance by having write through cache. This improves write performance as well.
- Just like DynamoDB, DAX is fully managed. You no longer need to worry about management tasks such as hardware or software provisioning, setup and configuration, software patching, operating a reliable, distributed cache cluster, or replicating data over multiple instances as you scale.
- This means there is no need for developers to manage the caching logic. DAX is completely compatible with existing DynamoDB API calls.
- DAX enables you to provision one DAX cluster for multiple DynamoDB tables, multiple DAX clusters for a single DynamoDB table or somewhere in between giving you maximal flexibility.
- DAX is designed for HA so in the event of a failure of one AZ, it will fail over to one of its replicas in another AZ. This is also managed automatically. 

### DynamoDB Streams:
- A DynamoDB stream is an ordered flow of information about changes to items in an Amazon DynamoDB table. When you enable a stream on a table, DynamoDB captures information about every modification to data items in the table.
- Amazon DynamoDB is integrated with AWS Lambda so that you can create triggers—pieces of code that automatically respond to events in DynamoDB Streams. 
- Immediately after an item in the table is modified, a new record appears in the table's stream. AWS Lambda polls the stream and invokes your Lambda function synchronously when it detects new stream records. The Lambda function can perform any actions you specify, such as sending a notification or initiating a workflow.
- With triggers, you can build applications that react to data modifications in DynamoDB tables.
- Whenever an application creates, updates, or deletes items in the table, DynamoDB Streams writes a stream record with the primary key attribute(s) of the items that were modified. A stream record contains information about a data modification to a single item in a DynamoDB table. You can configure the stream so that the stream records capture additional information, such as the "before" and "after" images of modified items.

### DynamoDB Global Tables
- Global Tables is a multi-region, multi-master replication solution for fast local performance of globally distributed apps.
- Global Tables replicates your Amazon DynamoDB tables automatically across your choice of AWS regions.
- It is based on DynamoDB streams and is multi-region redundant for data recovery or high availability purposes. Application failover is as simple as redirecting your application’s DynamoDB calls to another AWS region.
- Global Tables eliminates the difficult work of replicating data between regions and resolving update conflicts, enabling you to focus on your application’s business logic. You do not need to rewrite your applications to make use of Global Tables. 
- Replication latency with Global Tables is typically under one second.


## Redshift

### Redshift の概要:
 Amazon Redshiftは、フルマネージドでペタバイト規模のデータウェアハウスをクラウドで提供するサービスです。Amazon Redshiftサービスは、データウェアハウスのセットアップ、運用、スケーリングのすべての作業を管理します。これらの作業には、容量のプロビジョニング、クラスタの監視とバックアップ、Amazon Redshiftエンジンへのパッチとアップグレードの適用が含まれます。

### Redshift の詳細:
-  An Amazon Redshift cluster is a set of nodes which consists of a leader node and one or more compute nodes. The type and number of compute nodes that you need depends on the size of your data, the number of queries you will execute, and the query execution performance that you need. 
- Redshift is used for business intelligence and pulls in very large and complex datasets to perform complex queries in order to gather insights from the data.
- It fits the use case of Online Analytical Processing (OLAP). Redshift is a powerful technology for data discovery including capabilities for almost limitless report viewing, complex analytical calculations, and predictive “what if” scenario (budget, forecast, etc.) planning.
- Depending on your data warehousing needs, you can start with a small, single-node cluster and easily scale up to a larger, multi-node cluster as your requirements change. You can add or remove compute nodes to the cluster without any interruption to the service. 
- If you intend to keep your cluster running for a year or longer, you can save money by reserving compute nodes for a one-year or three-year period.
- Snapshots are point-in-time backups of a cluster. These backups are enabled by default with a 1 day retention period. The maximum retention period is 35 days.
- Redshift can also asynchronously replicate your snapshots to a different region if desired.
- A Highly Available Redshift cluster would require 3 copies of your data. One copy would be live in Redshift and the others would be standby in S3.
- Redshift can have up to 128 compute nodes in a multi-node cluster. The leader node always manages client connections and relays queries to the compute nodes which store the actual data and perform the queries.
- Redshift is able to achieve efficiency despite the many parts and pieces in its architecture through using columnar compression of data stores that contain similar data. In addition, Redshift does not require indexes or materialized views which means it can be relatively smaller in size compared to an OLTP database containing the same amount of information. Finally, when loading data into a Redshift table, Redshift will automatically down sample the data and pick the most appropriate compression scheme.
- Redshift also comes with Massive Parallel Processing (MPP) in order to take advantage of all the nodes in your multi-node cluster. This is done by evenly distributing data and query load across all nodes. Because of this, scaling out still retains great performance.
- Redshift is encrypted in transit using SSL and is encrypted at rest using AES-256. By default, Redshift will manage all keys, but you can do so too via AWS CloudHSM or AWS KMS.
- Redshift is billed for:
  - Compute Node Hours (total hours your non-leader nodes spent querying for data)
  - Backups
  - Data transfer within a VPC (but not outside of it)
- Redshift is not multi-AZ, if you want multi-AZ you will need to spin up a separate cluster ingesting the same input. You can also manually restore snapshots to a new AZ in the event of an outage.
- When you provision an Amazon Redshift cluster, it is locked down by default so nobody has access to it. To grant other users inbound access to an Amazon Redshift cluster, you associate the cluster with a security group.
- Amazon Redshift provides free storage for snapshots that is equal to the storage capacity of your cluster until you delete the cluster. After you reach the free snapshot storage limit, you are charged for any additional storage at the normal rate. Because of this, you should evaluate how many days you need to keep automated snapshots and configure their retention period accordingly, and delete any manual snapshots that you no longer need. 
- Regardless of whether you enable automated snapshots, you can take a manual snapshot whenever you want. Amazon Redshift will never automatically delete a manual snapshot. Manual snapshots are retained even after you delete your Redshift cluster. Because manual snapshots accrue storage charges, it’s important that you manually delete them if you no longer need them

## Redshift Spectrum:
- Amazon Redshift Spectrum is used to run queries against exabytes of unstructured data in Amazon S3, with no loading or ETL required.
- Redshift Spectrum queries employ massive parallelism to execute very fast against large datasets. Much of the processing occurs in the Redshift Spectrum layer, and most of the data remains in Amazon S3.
- Redshift Spectrum queries use much less of your cluster's processing capacity than other queries.
- The cluster and the data files in Amazon S3 must be in the same AWS Region.
- External S3 tables are read-only. You can't perform insert, update, or delete operations on external tables. 

## Redshift Enhanced VPC Routing:
- When you use Amazon Redshift Enhanced VPC Routing, Redshift forces all traffic (such as COPY and UNLOAD traffic) between your cluster and your data repositories through your Amazon VPC. 
- If Enhanced VPC Routing is not enabled, Amazon Redshift routes traffic through the Internet, including traffic to other services within the AWS network.
- By using Enhanced VPC Routing, you can use standard VPC features, such as VPC security groups, network access control lists (ACLs), VPC endpoints, VPC endpoint policies, internet gateways, and Domain Name System (DNS) servers.

  
## ElastiCache

### ElastiCache の概要:
ElastiCacheサービスは、クラウド上のインメモリキャッシュの導入、運用、拡張を容易にします。高スループットかつ低レイテンシのインメモリデータストアからデータを取得することで、既存のデータベースのパフォーマンスを高めることができます。

### ElastiCache の詳細:
- The service is great for improving the performance of web applications by allowing you to receive information locally instead of relying solely on relatively distant DBs.
- Amazon ElastiCache offers fully managed Redis and Memcached for the most demanding applications that require sub-millisecond response times.
- For data that doesn’t change frequently and is often asked for, it makes a lot of sense to cache said data rather than querying it from the database.
- Common configurations that improve DB performance include introducing read replicas of a DB primary and inserting a caching layer into the storage architecture. 
- Memcached is for simple caching purposes with horizontal scaling and multi-threaded performance, but if you require more complexity for your caching environment then choose Redis.
- A further comparison between MemcacheD and Redis for ElastiCache:
![Screen Shot 2020-06-18 at 8 18 34 PM](https://user-images.githubusercontent.com/13093517/85083820-edc1b480-b1a0-11ea-88b0-15f90bd60282.png)

- Another advantage of using ElastiCache is that by caching query results, you pay the price of the DB query only once without having to re-execute the query unless the data changes.
- Amazon ElastiCache can scale-out, scale-in, and scale-up to meet fluctuating application demands. Write and memory scaling is supported with sharding. Replicas provide read scaling.

## Route53

### Route53 の概要:
Amazon Route 53は、可用性と拡張性の高いドメインネームシステム（DNS）サービスです。Route 53を使用して、3つの主な機能（ドメイン登録、DNSルーティング、ヘルスチェック）を自由に組み合わせて実行できます。

### Route53 の詳細:
- DNS is used to map human-readable domain names into an internet protocol address similarly to how phone books map company names with phone numbers.
- AWS has its own domain registrar.
- When you buy a domain name, every DNS address starts with an SOA (Start of Authority) record. The SOA record stores information about the name of the server that kicked off the transfer of ownership, the administrator who will now use the domain, the current metadata available, and the default number of seconds or TTL. 
- NS records, or Name Server records, are used by the Top Level Domain hosts (.org, .com, .uk, etc.) to direct traffic to the Content servers. The Content DNS servers contain the authoritative DNS records.
- Browsers talk to the Top Level Domains whenever they are queried and encounter domain name that they do not recognize.
  1. Browsers will ask for the authoritative DNS records associated with the domain.
  2. Because the Top Level Domain contains NS records, the TLD can in turn query the Name Servers for their own SOA.
  3. Within the SOA, there will be the requested information.
  4. Once this information is collected, it will then be returned all the way back to the original browser asking for it.
- In summary: Browser -> TLD -> NS -> SOA -> DNS record. The pipeline reverses when the correct DNS record is found.
- Authoritative name servers store DNS record information, usually a DNS hosting provider or domain registrar like GoDaddy that offers both DNS registration and hosting.
- There are a multitude of DNS records for Route53. Here are some of the more common ones:
  - **A records**: These are the fundamental type of DNS record. The “A” in A records stands for “address”. These records are used by a computer to directly pair a domain name to an IP address. IPv4 and IPv6 are both supported with "AAAA" referring to the IPv6 version. **A: URL -> IPv4** and **AAAA: URL -> IPv6**.
  - **CName records**: Also referred to as the Canonical Name. These records are used to resolve one domain name to another domain name. For example, the domain of the mobile version of a website may be a CName from the domain of the browser version of that same website rather than a separate IP address. This would allow mobile users who visit the site and to receive the mobile version. **CNAME: URL -> URL**.
  - **Alias records**: These records are used to map your domains to AWS resources such as load balancers, CDN endpoints, and S3 buckets. Alias records function similarly to CNames in the sense that you map one domain to another. The key difference though is that by pointing your Alias record at a service rather than a domain name, you have the ability to freely change your domain names if needed and not have to worry about what records might be mapped to it. Alias records give you dynamic functionality. **Alias: URL -> AWS Resource**.
  - **PTR records**: These records are the opposite of an A record. PTR records map an IP to a domain and they are used in reverse DNS lookups as a way to obtain the domain name of an IP address. **PTR: IPv4 -> URL**. 
- One other major difference between CNames and Alias records is that a CName cannot be used for the naked domain name (the apex record in your entire DNS configuration / the primary record to be used). CNames must always be secondary records that can map to another secondary record or the apex record. The primary must always be of type Alias or A Record in order to work.
- Due to the dynamic nature of Alias records, they are often recommended for most use cases and should be used when it is possible to.
- TTL is the length that a DNS record is cached on either the resolving servers or the users own cache so that a fresher mapping of IP to domain can be retrieved. Time To Live is measured in seconds and the lower the TTL the faster DNS changes propagate across the internet. Most providers, for example, have a TTL that lasts 48 hours.
- You can create health checks to send you a Simple Notification if any issues arise with your DNS setup.
- Further, Route53 health checks can be used for any AWS endpoint that can be accessed via the Internet. This makes it an ideal option for monitoring the health of your AWS endpoints.

### Route53 Routing Policies:
- When you create a record, you choose a routing policy, which determines how Amazon Route 53 responds to DNS queries. The routing policies available are:
  - Simple Routing
  - Weighted Routing
  - Latency-based Routing
  - Failover Routing
  - Geolocation Routing
  - Geo-proximity Routing
  - Multivalue Answer Routing
- **Simple Routing** is used when you just need a single record in your DNS with either one or more IP addresses behind the record in case you want to balance load. If you specify multiple values in a Simple Routing policy, Route53 returns a random IP from the options available.
- **Weighted Routing** is used when you want to split your traffic based on assigned weights. For example, if you want 80% of your traffic to go to one AZ and the rest to go to another, use Weighted Routing. This policy is very useful for testing feature changes and due to the traffic splitting characteristics, it can double as a means to perform blue-green deployments. When creating Weighted Routing, you need to specify a new record for each IP address. You cannot group the various IPs under one record like with Simple Routing.
- **Latency-based Routing**, as the name implies, is based on setting up routing based on what would be the lowest latency for a given user. To use latency-based routing, you must create a latency resource record set in the same region as the corresponding EC2 or ELB resource receiving the traffic. When Route53 receives a query for your site, it selects the record set that gives the user the quickest speed. When creating Latency-based Routing, you need to specify a new record for each IP.
- **Failover Routing** is used when you want to configure an active-passive failover set up. Route53 will monitor the health of your primary so that it can failover when needed. You can also manually set up health checks to monitor all endpoints if you want more detailed rules.
- **Geolocation Routing** lets you choose where traffic will be sent based on the geographic location of your users.
- **Geo-proximity Routing** lets you choose where traffic will be sent based on the geographic location of your users *and* your resources. You can choose to route more or less traffic based on a specified weight which is referred to as a bias. This bias either expands or shrinks the availability of a geographic region which makes it easy to shift traffic from resources in one location to resources in another. To use this routing method, you must enable Route53 traffic flow. If you want to control global traffic, use Geo-proximity routing. If you want traffic to stay in a local region, use Geolocation routing.
- **Multivalue Routing** is pretty much the same as Simple Routing, but Multivalue Routing allows you to put health checks on each record set. This ensures then that only a healthy IP will be randomly returned rather than any IP.

## Elastic Load Balancers (ELB)

### ELB の概要:
Elastic Load Balancingは、Amazon EC2インスタンス、Dockerコンテナ、IPアドレス、Lambda関数など、複数のターゲットに受信するアプリケーショントラフィックを自動的に分散します。単一のアベイラビリティ・ゾーン、または複数のアベイラビリティ・ゾーンにまたがるアプリケーション・トラフィックのさまざまな負荷に対応できます。Elastic Load Balancingは3種類のロードバランサーを提供しており、いずれもアプリケーションのフォールトトレラントに必要な高可用性、自動スケーリング、堅牢なセキュリティを備えています。

### ELB の詳細:
- Load balancers can be internet facing or application internal.
- To route domain traffic to an ELB load balancer, use Amazon Route 53 to create an Alias record that points to your load balancer. An Alias record is preferable over a CName, but both can work.
- ELBs do not have predefined IPv4 addresses; you must resolve them with DNS instead. Your load balancer will never have its own IP by default, but you can create a static IP for a network load balancer because network LBs are for high performance purposes.
- Instances behind the ELB are reported as `InService` or `OutOfService`.
When an EC2 instance behind an ELB fails a health check, the ELB stops sending traffic to that instance.
- A dual stack configuration for a load balancer means load balancing over IPv4 and IPv6
- In AWS, there are three types of LBs:
  - Application LBs
  - Network LBs
  - Classic LBs.
- **Application LBs** are best suited for HTTP(S) traffic and they balance load on layer 7 OSI. They are intelligent enough to be application aware and Application Load Balancers also support path-based routing, host-based routing and support for containerized applications. As an example, if you change your web browser’s language into French, an Application LB has visibility of the metadata it receives from your browser which contains details about the language you use. To optimize your browsing experience, it will then route you to the French-language servers on the backend behind the LB. You can also create advanced request routing, moving traffic into specific servers based on rules that you set yourself for specific cases.
- **Network LBs** are best suited for TCP traffic where performance is required and they balance load on layer 4. They are capable of managing millions of requests per second while maintaining extremely low latency.
- **Classic LBs** are the legacy ELB product and they balance either on HTTP(S) or TCP, but not both. Even though they are the oldest LBs, they still support features like sticky sessions and X-Forwarded-For headers.
- If you need flexible application management and TLS termination then you should use the Application Load Balancer. If extreme performance and a static IP is needed for your application then you should use the Network Load Balancer. If your application is built within the EC2 Classic network then you should use the Classic Load Balancer.
- The lifecycle of a request to view a website behind an ELB:
  1. The browser requests the IP address for the load balancer from DNS.
  2. DNS provides the IP.
  3. With the IP at hand, your browser then makes an HTTP request for an HTML page from the Load Balancer.
  4. AWS perimeter devices checks and verifies your request before passing it onto the LB.
  5. The LB finds an active webserver to pass on the HTTP request.
  6. The webserver returns the requested HTML file.
  7. The browser receives the HTML file it requested and renders the graphical representation of it on the screen.
- Load balancers are a regional service. They do not balance load across different regions. You must provision a new ELB in each region that you operate out of.
- If your application stops responding, you’ll receive a 504 error when hitting your load balancer. This means the application is having issues and the error could have bubbled up to the load balancer from the services behind it. It does not necessarily mean there's a problem with the LB itself.

### ELB Advanced Features:
- To enable IPv6 DNS resolution, you need to create a second DNS resource record so that the **ALIAS AAAA** record resolves to the load balancer along with the IPv4 record.
- The X-Forwarded-For header, via the Proxy Protocol, is simply the idea for load balancers to forward the requester's IP address along with the actual request for information from the servers behind the LBs. Normally, the servers behind the LBs only see that the IP sending it traffic belongs to the Load Balancer. They usually have no idea about the true origin of the request as they only know about the computer (the LB) that asks them to do something. But sometimes we may want to route the original IP to the backend servers for specific use cases and have the LB’s IP address ignored. The X-Forwarded-For header makes this possible.
- Sticky Sessions bind a given user to a specific instance throughout the duration of their stay on the application or website. This means all of their interactions with the application will be directed to the same host each time. If you need local disk for your application to work, sticky sessions are great as users are guaranteed consistent access to the same ephemeral storage on a particular instance. The downside of sticky sessions is that, if done improperly, it can defeat the purpose of load balancing. All traffic could hypothetically be bound to the same instance instead of being evenly distributed.
- Path Patterns create a listener with rules to forward requests based on the URL path set within those user requests. This method, known as path-based routing, ensures that traffic can be specifically directed to multiple back-end services. 
For example, with Path Patterns you can route general requests to one target group and requests to render images to another target group. So the URL, “www.example.com/” will be forwarded to a server that is used for general content while “www.example.com/photos” will be forwarded to another server that renders images.


### ELB Cross Zone Load Balancing:
- Cross Zone load balancing guarantees even distribution across AZs rather than just within a single AZ.
- If Cross Zone load balancing is disabled, each load balancer node distributes requests evenly across the registered instances in its Availability Zone only. 
- Cross Zone load balancing reduces the need to maintain equivalent numbers of instances in each enabled Availability Zone, and improves your application's ability to handle the loss of one or more instances.
- However, it is still recommend that you maintain approximately equivalent numbers of instances in each enabled Availability Zone for higher fault tolerance. 
- For environments where clients cache DNS lookups, incoming requests might favor one of the Availability Zones. Using Cross Zone load balancing, this imbalance in the request load is spread across all available instances in the region instead.

### ELB Security:
- ELB supports SSL/TLS & HTTPS termination. Termination at load balancer is desired because decryption is resource and CPU intensive. Putting the decryption burden on the load balancer enables the EC2 instances to spend their processing power on application tasks, which helps improve overall performance.
-  Elastic Load Balancers (along with CloudFront) support Perfect Forward Secrecy. This is a feature that provides additional safeguards against the eavesdropping of encrypted data in transit through the use of a uniquely random session key. This is done by ensuring that the in-use part of an encryption system automatically and frequently changes the keys it uses to encrypt and decrypt information. So if this latest key is compromised at all, it will only expose a small portion of the user's recent data.
- Classic Load Balancers do not support Server Name Indication (SNI). SNI allows the server (the LB in this case) to safely host multiple TLS Certificates for multiple sites all under a single IP address (the Alias record or CName record in this case). To allow SNI, you have to use an Application Load Balancer instead or use it with a CloudFront web distribution. 

## Auto Scaling

### Auto Scaling の概要:
AWS Auto Scalingは、異なるリソースのグループが需要の変化にどのように対応するかを自動化するスケーリングプランを構築できます。可用性、コスト、またはその両方のバランスを最適化できます。AWS Auto Scalingは、すべてのスケーリングポリシーを自動的に作成し、お客様の好みに基づいてターゲットを設定します。

### Auto Scaling の詳細:
- Auto Scaling is a major benefit from the cloud's economies of scale so if you ever have a requirement for scaling, automatically think of using the Auto Scaling service. 
- Auto Scaling has three components:
  - **Groups**: These are logical components. A webserver group of EC2 instances, a database group of RDS instances, etc.
  - **Configuration Templates**: Groups use a template to configure and launch new instances to better match the scaling needs. You can specify information for the new instances like the AMI to use, the instance type, security groups, block devices to associate with the instances, and more.
  - **Scaling Options**: Scaling Options provides several ways for you to scale your Auto Scaling groups. You can base the scaling trigger on the occurrence of a specified condition or on a schedule.
- The following image highlights the state of an Auto scaling group. The orange squares represent active instances. The dotted squares represent potential instances that can and will be spun up whenever necessary. The minimum number, the maximum number, and the desired capacity of instances are all entirely configurable.

![Screen Shot 2020-06-19 at 4 44 18 PM](https://user-images.githubusercontent.com/13093517/85178368-50bc5580-b24c-11ea-9acc-45ca5742e889.png)

- When you use Auto Scaling, your applications gain the following benefits: 
  - **Better fault tolerance**: Auto Scaling can detect when an instance is unhealthy, terminate it, and launch an instance to replace it. You can also configure Auto Scaling to use multiple Availability Zones. If one Availability Zone becomes unavailable, Auto Scaling can launch instances in another one to compensate. 
  - **Better availability**: Auto Scaling can help you ensure that your application always has the right amount of capacity to handle the current traffic demands. 
- When it comes to actually scale your instance groups, the Auto Scaling service is flexible and can be done in various ways:
  - Auto Scaling can scale based on the demand placed on your instances. This option automates the scaling process by specifying certain thresholds that, when reached, will trigger the scaling. This is the most popular implementation of Auto Scaling.
  - Auto Scaling can ensure the current number of instances at all times. This option will always maintain the number of servers you want running even when they fail.
  - Auto Scaling can scale only with manual intervention. If you want to control all of the scaling yourself, this option makes sense.
  - Auto Scaling can scale based on a schedule. If you can reliably predict spikes in traffic, this option makes sense.
  - Auto Scaling based off of predictive scaling. This option lets AWS AI/ML learn more about your environment in order to predict the best time to scale for both performance improvements and cost-savings.
- In maintaining the current running instance, Auto Scaling will perform occasional health checks on the running instances to ensure that they are all healthy. When the service detects that an instance is unhealthy, it will terminate that instance and then bring up a new one online.
- When designing HA for your Auto Scaling, use multiple AZs and multiple regions wherever you can.
- Auto Scaling allows you to suspend and then resume one or more of the Auto Scaling processes in your Auto Scaling Group. This can be very useful when you want to investigate a problem in your application without triggering the Auto Scaling process when making changes.
- You can specify your launch configuration with multiple Auto Scaling groups. However, you can only specify one launch configuration for an Auto Scaling group at a time.
- You cannot modify a launch configuration after you've created it. If you want to change the launch configuration for an Auto Scaling group, you must create a new launch configuration and update your Auto Scaling group to inherit this new launch configuration.

### Auto Scaling Default Termination Policy:
- The default termination policy for an Auto Scaling Group is to automatically terminate a stopped instance, so unless you've configured it to do otherwise, stopping an instance will result in termination regardless if you wanted that to happen or not. A new instance will be spun up in its place. 
- The default termination policy will spare instances that you tell it in case some servers are running critical systems or applications. These critical servers are protected from "scale in", which is just the deletion process of instances deemed superfluous to requirements.
- The default termination policy is designed to help ensure that your network architecture spans Availability Zones evenly. With the default termination policy, the behavior of the Auto Scaling group is as follows:
  - If there are instances in multiple Availability Zones, it will terminate an instance from the Availability Zone with the most instances. If there is more than one Availability Zone with the same max number of instances, it will choose the Availability Zone where instances use the oldest launch configuration.
  - It will then determine which unprotected instances in the selected Availability Zone use the oldest launch configuration. If there is one such instance, it will terminate it.
  - If there are multiple instances to terminate, it will determine which unprotected instances are closest to the next billing hour. (This helps you maximize the use of your EC2 instances and manage your Amazon EC2 usage costs.) If there are some instances that match this criteria, they will be terminated.
- This flow chart can provide further clarity on how the default Auto Scaling policy decides which instances to delete:

![Screen Shot 2020-06-19 at 5 19 02 PM](https://user-images.githubusercontent.com/13093517/85180270-0093c200-b251-11ea-97e3-ed9a80ee5d65.png)

## Auto Scaling Cooldown Period:
- クールダウン期間は、Auto Scaling Groupに対して構成可能な設定であり、前回のスケーリングアクティビティが有効になる前に追加のインスタンスを起動または終了しないようにするのに役立ちます。
- ポリシーを使用してAuto Scaling Groupがスケーリングした後、クールダウン期間が完了するのを待ってから、必要に応じてスケーリング活動を再開します。
- デフォルトの待機期間は300秒ですが、これは変更できます。

## Virtual Private Cloud (VPC)

### VPC の概要:
VPCを使用すると、AWSクラウドの論理的に隔離されたセクションをプロビジョニングし、定義した仮想ネットワーク内でサービスやシステムを起動することができます。どのAWSリソースをパブリックにし、どのリソースをパブリックにしないかを選択するオプションがあることで、VPCはセキュリティに対してよりきめ細かいコントロールを提供します。

### VPC の詳細:
- You can think of VPC as your own virtual data center in the cloud. You have complete control of your own network; including the IP range, the creation of sub-networks (subnets), the configuration of route tables and the network gateways used.
- You can then launch EC2 instances into a subnet of your choosing, select the IPs to be available for the instances, assign security groups for them, and create Network Access Control Lists (NACLs) for the subnets themselves as additional protection.
- This customization gives you much more control to specify and personalize your infrastructure setup. For example, you can have one public-facing subnet for your web servers to receive HTTP traffic and then a different private-facing subnet for your database server where internet access is forbidden.
- You use subnets to efficiently utilize networks that have a large number of hosts
- VPCs come with defense in depth by design. From the sub-network (NACLs) down to the individual server (security group) and further down to the application itself (secure coding practices), you can set up multiple levels of protection against malicious users and programs.
- The default VPC for your AWS environment permits all subnets to have a route out to the internet meaning all subnets in the default VPC are internet accessible. The default setting allows you to immediately deploy instances and each EC2 instance will have both a public and private IP address.
- There is one default VPC per region. However, you can have as many custom VPCs as you want and all are private by default.
- When you create a custom VPC, new subnets are not created by default. You must create them separately. The same is true for an internet gateway. If you want your VPC to have internet access, you need to also create the gateway so that the network can be reached publicly by the world.
- Because of this, when you create an IGW it will initially be in an detached state. You will need to manually assign it to the custom VPC.
- Once you create a custom VPC however, the following are created by default:
  - a route table
  - a NACL
  - a security group
  
![Screen Shot 2020-06-19 at 6 26 37 PM](https://user-images.githubusercontent.com/13093517/85183681-8cf6b280-b25a-11ea-8b54-d1e54ba754a6.png)

- These components, which will be explained in further depth in case they are not already known, actually correspond to the traffic flow for how data will reach your instances. Whether the traffic originates from outside of the VPC or from within it, it must first go through the route table by way of the router in order to know where the desired destination is. Once that is known, the traffic then passes through subnet level security as described by the NACL. If the NACL deems the traffic as valid, the traffic then passes through to the instance level security as described by the security group. If the traffic hasn't been dropped at this point, only then will it reach its intended instance.
- The VPC Wizard is an automated tool that is useful for creating custom VPCs.
- You can have your VPC on dedicated hardware so that the network is exclusive at the physical level, but this option is extremely expensive. Fortunately, if a VPC is on dedicated hosting it can always be changed back to the default hosting. This can be done via the AWS CLI, SDK or API. However, existing hosts on the dedicated hardware must first be in a `stopped` state.
-  When you create a VPC, you must assign it an IPv4 CIDR block. This CIDR block is a range of private IPv4 addresses that will be inherited by your instances when you create them.
- The IP range of a default VPC is always **/16**.
- When creating IP ranges for your subnets, the **/16** CIDR block is the largest range of IPs that can be used. This is because subnets must have just as many IPs or fewer IPs than the VPC it belongs to. A **/28** CIDR block is the smallest IP range available for subnets.
- With CIDR in general, a **/32** denotes a single IP address and **/0** refers to the entire network. The higher you go in CIDR, the more narrow the IP range will be.
- The above information about IPs is in regards to both public and private IP addresses. 
- Private IP addresses are not reachable over the Internet and instead are used for communication between the instances in your VPC. When you launch an instance into a VPC, a private IP address from the IPv4 address range of the subnet is assigned to the default network interface (eth0) of the instance.
- This means that all instances within a VPC have a private IP, but only those selected to communicate with the external world have a public IP.
- When you launch an instance into a subnet that has public access via an Internet Gateway, both a public IP address and a private IP address are created. The public IP address is instead assigned to the primary network interface (eth0) that's created for the instance. Externally, the public IP address is mapped to the private IP address through network address translation (NAT). 
- You can optionally associate an IPv6 CIDR block with your VPC and subnets, and assign IPv6 addresses from that block to the resources in your VPC.
- VPCs are region specific and you can have up to five VPCs per region.
- By default, AWS is configured to have one subnet in each AZ of the regions where your application is.
- In an ideal and secure VPC architecture, you launch the web servers or elastic load balancers in the public subnet and the database servers in the private subnet.
- Here is an example of a hypothetical application sitting behind a typical VPC setup:

![Screen Shot 2020-06-21 at 6 20 09 PM](https://user-images.githubusercontent.com/13093517/85236432-dd514a00-b3eb-11ea-9ab0-1b5acf4b8894.png)

- Security groups can span subnets, but do not span VPCs. ICMP ensures that instances from one security group can ping others in a different security group. It is IPv4 and IPv6 compatible.

### VPC Subnets:
- If a network has a large number of hosts without logically grouped subdivisions, managing the many hosts can be a tedious job. Therefore you use subnets to divide a network so that management becomes easier.
- When you create a subnet, be sure to specify which VPC you want to place it in. You can assign both IPv4 and IPv6 ranges to your subnets.
- The main benefits of subnets:
  - They improve traffic flow, and thus speed & performance of the entire network. An Internet gateway (IGW) receiving a packet and checking which of 5 subnets the packet should be delivered to is much faster than checking 100 instances individually. And if the destination of a packet is within the subnet from where it originates, the traffic stays inside the subnet and doesn't clutter the rest of the VPC.
  - Subnets function as logical groups to put your entities inside of. It makes it much easier to configure similar resources as a group instead of for every individual instance.
- Amazon always reserves five IP addresses within a subnet. The first four IP addresses and the last IP address of each subnet CIDR block will always be unavailable for use.

### Network Access Control Lists:
- Network Access Control Lists (or NACLs) are like security groups but for subnets rather than instances. The main difference between security groups and NACLs is that security groups are *stateful*, meaning you can perform both allow and deny rules that may be divergent, depending if traffic is inbound or outbound, for that rule. 
- The following table highlights the differences between NACLs and Subnets. 

| NACL | Security Group |
| ------------- | ------------- |
| Operates at the subnet level | Operates at the instance level | 
| Supports allow rules and deny rules  | Supports allow rules only |
| Is stateless: Return traffic must be explicitly allowed by rules  |  Is stateful: Return traffic is automatically allowed, regardless of any rules |
| We process rules in order, starting with the lowest numbered rule, when deciding whether to allow traffic  |  We evaluate all rules before deciding whether to allow traffic |
| Automatically applies to all instances in the subnets that it's associated with (therefore, it provides an additional layer of defense if the security group rules are too permissive) |  Applies to an instance only if someone specifies the security group when launching the instance, or associates the security group with the instance later on |
- Because NACLs are stateless, you must also ensure that outbound rules exist alongside the inbound rules so that ingress and egress can flow smoothly.
- The default NACL that comes with a new VPC has a default rule to allow all inbounds and outbounds. This means that it exists, but doesn't do anything as all traffic passes through it freely.
- However, when you create a new NACL (instead of using the default that comes with the VPC) the default rules will deny all inbounds and outbounds. 
- If you create a new NACL, you must associate whichever desired subnets to it manually so that they can inherit the NACL’s rule set. If you don’t explicitly assign a subnet to an NACL, AWS will associate it with your default NACL.
- NACLs are evaluated before security groups and you block malicious IPs with NACLs, not security groups.
- A subnet can only follow the rules listed by one NACL at a time. However, a NACL can describe the rules for any number of subnets. The rules will take effect immediately.
- Network ACL rules are evaluated by rule number, from lowest to highest, and executed immediately when a matching allow/deny rule is found. Because of this, order matters with your rule numbers. 
- The lower the number of a rule on the list, the more seniority that rule will have. List your rules accordingly. 

- If you are using NAT Gateway along with your NACL, you must ensure the availability of the NAT Gateway ephemeral port range within the rules of your NACL. Because NAT Gateway traffic can appear on any of range's ports for the duration of its connection, you must ensure that all possible ports are accounted for and open.
- NACL can have a small impact on how EC2 instances in a private subnet will communicate with any service, including VPC Endpoints.


### NAT Instances vs. NAT Gateways:
- Attaching an Internet Gateway to a VPC allows instances with public IPs to directly access the internet. NAT does a similar thing, however it is for instances that do not have a public IP. It serves as an intermediate step which allow private instances to first mask their own private IP as the NAT's public IP before accessing the internet.
- You would want your private instances to access the internet so that they can have normal software updates. NAT prevents any initiating of a connection from the internet.
- **NAT instances** are individual EC2 instances that perform the function of providing private subnets a means to securely access the internet. 
- Because they are individual instances, High Availability is not a built-in feature and they can become a choke point in your VPC. They are not fault-tolerant and serve as a single point of failure. While it is possible to use auto-scaling groups, scripts to automate failover, etc. to prevent bottlenecking, it is far better to use the NAT Gateway as an alternative for a scalable solution.
- **NAT Gateway** is a managed service that is composed of multiple instances linked together within an availability zone in order to achieve HA by default.
- To achieve further HA and a zone-independent architecture, create a NAT gateway for each Availability Zone and configure your routing to ensure that resources use the NAT gateway in their corresponding Availability Zone. 
- NAT instances are deprecated, but still useable. NAT Gateways are the preferred means to achieve Network Address Translation. 
- There is no need to patch NAT Gateways as the service is managed by AWS. You do need to patch NAT Instances though because they’re just individual EC2 instances.
- Because communication must always be initiated from your private instances, you need a route rule to route traffic from a private subnet to your NAT gateway.
- Your NAT instance/gateway will have to live in a public subnet as your public subnet is the subnet configured to have internet access.
- When creating NAT instances, it is important to remember that EC2 instances have source/destination checks on them by default. What these checks do is ensure that any traffic it comes across must be either generated by the instance or be the intended recipient of that traffic. Otherwise, the traffic is dropped because the EC2 instance is neither the source nor the destination.
- So because NAT instances act as a sort of proxy, you *must* disable source/destination checks when musing a NAT instance.

### Bastion Hosts:
- Bastion Hosts are special purpose computers designed and configured to withstand attacks. This server generally runs a single program and is stripped beyond this purpose in order to reduce attack vectors. 
- The purpose of Bastion Hosts are to remotely access the instances behind the private subnet for system administration purposes without exposing the host via an internet gateway. 
- The best way to implement a Bastion Host is to create a small EC2 instance that only has a security group rule for a single IP address. This ensures maximum security.
- It is perfectly fine to use a small instance rather than a large one because the instance will only be used as a jump server that connects different servers to each other.
- If you are going to RDP or SSH into the instances of your private subnet, use a Bastion Host. If you are going to be providing internet traffic into the instances of your private subnet, use a NAT.
- Similar to NAT Gateways and NAT Instances, Bastion Hosts live within a public-facing subnet.
- There are pre-baked Bastion Host AMIs.

### Route Tables:
- Route tables are used to make sure that subnets can communicate with each other and that traffic knows where to go.
- Every subnet that you create is automatically associated with the main route table for the VPC.
- You can have multiple route tables. If you do not want your new subnet to be associated with the default route table, you must specify that you want it associated with a different route table.
- Because of this default behavior, there is a potential security concern to be aware of: if the default route table is public then the new subnets associated with it will also be public. 
- The best practice is to ensure that the default route table where new subnets are associated with is private.
- This means you ensure that there is no route out to the internet for the default route table. Then, you can create a custom route table that is public instead. New subnets will automatically have no route out to the internet. If you want a new subnet to be publicly accessible, you can simply associate it with the custom route table.
- Route tables can be configured to access endpoints (public services accessed privately) and not just the internet.

### Internet Gateway:
- If the Internet Gateway is not attached to the VPC, which is the prerequisite for instances to be accessed from the internet, then naturally instances in your VPC will not be reachable. 
- If you want all of your VPC to remain private (and not just some subnets), then do not attach an IGW.
- When a Public IP address is assigned to an EC2 instance, it is effectively registered by the Internet Gateway as a valid public endpoint. However, each instance is only aware of its private IP and not its public IP. Only the IGW knows of the public IPs that belong to instances. 
- When an EC2 instance initiates a connection to the public internet, the request is sent using the public IP as its source even though the instance doesn't know a thing about it. This works because the IGW performs its own NAT translation where private IPs are mapped to public IPs and vice versa for traffic flowing into and out of the VPC. 
- So when traffic from the internet is destined for an instance's public IP endpoint, the IGW receives it and forwards the traffic onto the EC2 instance using its internal private IP.
- You can only have one IGW per VPC.
- **Summary**: IGW connects *your VPC with the internet*.

### Virtual Private Networks (VPNs):
- VPCs can also serve as a bridge between your corporate data center and the AWS cloud. With a VPC Virtual Private Network (VPN), your VPC becomes an extension of your on-prem environment.
- Naturally, your instances that you launch in your VPC can't communicate with your own on-premise servers. You can allow the access by first:
  - attaching a virtual private gateway to the VPC
  - creating a custom route table for the connection
  - updating your security group rules to allow traffic from the connection
  - creating the managed VPN connection itself.
- To bring up VPN connection, you must also  define a customer gateway resource in AWS, which provides AWS information about your customer gateway device. And you have to set up an Internet-routable IP address of the customer gateway's external interface.
- A customer gateway is a physical device or software application on the on-premise side of the VPN connection.
- Although the term "VPN connection" is a general concept, a VPN connection for AWS always refers to the connection between your VPC and your own network. AWS supports Internet Protocol security (IPsec) VPN connections.
- The following diagram illustrates a single VPN connection.

![Screen Shot 2020-06-21 at 6 13 17 PM](https://user-images.githubusercontent.com/13093517/85236301-e857aa80-b3ea-11ea-9de9-08d150d34864.png)

- The above VPC has an attached virtual private gateway (note: not an internet gateway) and there is a remote network that includes a customer gateway which you must configure to enable the VPN connection. You set up the routing so that any traffic from the VPC bound for your network is routed to the virtual private gateway.
- **Summary**: VPNs connect your *on-prem with your VPC* over the internet.


### AWS DirectConnect:
- Direct Connect is an AWS service that establishes a dedicated network connection between your premises and AWS. You can create this private connectivity to reduce network costs, increase bandwidth, and provide more consistent network experience compared to regular internet-based connections.
- The use case for Direct Connect is high throughput workloads or if you need a stable or reliable connection
- VPN connects to your on-prem over the internet and DirectConnect connects to your on-prem off through a private tunnel.
- The steps for setting up an AWS DirectConnect connection:
  1. Create a virtual interface in the DirectConnect console. This is a public virtual interface.
  2. Go to the VPC console and then VPN connections. Create a customer gateway for your on-premise.
  3. Create a virtual private gateway and attach it to the desired VPC environment.
  4. Select VPN connections and create a new VPN connection. Select both the customer gateway and the virtual private gateway.
  5. Once the VPN connection is available, set up the VPN either on the customer gateway or the on-prem firewall itself
- Data flow into AWS via DirectConnect looks like the following: On-prem router -> dedicated line -> your own cage / DMZ -> cross connect line -> AWS Direct Connect Router -> AWS backbone -> AWS Cloud
- **Summary**: DirectConnect connects your *on-prem with your VPC* through a non-public tunnel.


### VPC Endpoints:
- VPC Endpoints ensure that you can connect your VPC to supported AWS services without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect. Traffic between your VPC and other AWS services stay within the Amazon ecosystem and these Endpoints are virtual devices that are HA and without bandwidth constraints. 
- These work basically by attaching an ENI to an EC2 instance that can easily communicate to a wide range of AWS services.
- **Gateway Endpoints** rely on creating entries in a route table and pointing them to private endpoints used for S3 or DynamoDB. Gateway Endpoints are mainly just a target that you set. 
- **Interface Endpoints** use AWS PrivateLink and have a private IP address so they are their own entity and not just a target in a route table.  Because of this, they cost $.01/hour. Gateway Endpoints are free as they’re just a new route in to set.
- Interface Endpoint provisions an Elastic Network interface or ENI (think network card) within your VPC. They serve as an entry and exit for traffic going to and from another supported AWS service. It uses a DNS record to direct your traffic to the private IP address of the interface. Gateway Endpoint uses route prefix in your route table to direct traffic meant for S3 or DynamoDB to the Gateway Endpoint (think 0.0.0.0/0 -> igw).
- To secure your Interface Endpoint, use Security Groups. But to secure Gateway Endpoint, use VPC Endpoint Policies.
- **Summary**: VPC Endpoints connect your *VPC with AWS services* through a non-public tunnel.

### AWS PrivateLink:
- AWS PrivateLink simplifies the security of data shared with cloud-based applications by eliminating the exposure of data to the public Internet. AWS PrivateLink provides private connectivity between different VPCs, AWS services, and on-premises applications, securely on the Amazon network.
- It's similar to the AWS Direct Connect service in that it establishes private connections to the AWS cloud, except Direct Connect links on-premises environments to AWS. PrivateLink, on the other hand, secures traffic from VPC environments which are already in AWS.
- This is useful because different AWS services often talk to each other over the internet. If you do not want that behavior and instead want AWS services to only communicate within the AWS network, use AWS PrivateLink. By not traversing the Internet, PrivateLink reduces the exposure to threat vectors such as brute force and distributed denial-of-service attacks. 
- PrivateLink allows you to publish an "endpoint" that others can connect with from their own VPC. It's similar to a normal VPC Endpoint, but instead of connecting to an AWS service, people can connect to your endpoint.
- Further, you'd want to use private IP connectivity and security groups so that your services function as though they were hosted directly on your private network.
- Remember that AWS PrivateLink applies to Applications/Services communicating with each other within the AWS network. For VPCs to communicate with each other within the AWS network, use VPC Peering.
- **Summary:** AWS PrivateLink connects your *AWS services with other AWS services* through a non-public tunnel.

### VPC Peering:
- VPC peering allows you to connect one VPC with another via a direct network route using the Private IPs belonging to both. With VPC peering, instances in different VPCs behave as if they were on the same network.
- You can create a VPC peering connection between your own VPCs, regardless if they are in the same region or not, and with a VPC in an entirely different AWS account.
- VPC Peering is usually done in such a way that there is one central VPC that peers with others. Only the central VPC can talk to the other VPCs.
- You cannot do transitive peering for non-central VPCs. Non-central VPCs cannot go through the central VPC to get to another non-central VPC. You must set up a new portal between non-central nodes if you need them to talk to each other.
- The following diagram highlights the above idea. VPC B is free to communicate with VPC A with VPC Peering enabled between both. However, VPC B cannot continue the conversation with VPC C. Only VPC A can communicate with VPC C.

![Screen Shot 2020-06-19 at 6 12 02 PM](https://user-images.githubusercontent.com/13093517/85183188-e1009780-b258-11ea-8a81-ad0612cd1053.png)

- It is worth knowing what VPC peering configurations are not supported:
  - Overlapping CIDR Blocks
  - Transitive Peering
  - Edge to Edge Routing through a gateway or connection device (VPN connection, Internet Gateway, AWS Direct Connect connection, etc.)
- You can peer across regions, but you cannot have one subnet stretched over multiple availability zones. However, you can have multiple subnets in the same availability zone.  
- **Summary**: VPC Peering connects your *VPC to another VPC* through a non-public tunnel.

### VPC Flow Logs:
- VPC Flow Logs is a feature that captures the IP information for all traffic flowing into and out of your VPC. Flow log data is sent to an S3 bucket or CloudWatch where you can view, retrieve, and manipulate this data. 
- You can capture the traffic flow at various stages through its travel:
  - Traffic flowing into and out of the VPC (like at the IGW)
  - Traffic flowing into and out of the subnet
  - Traffic flowing into and out of the network interface of the EC2 instance (eth0, eth1, etc.)
- VPS Flow Logs capture packet metadata and not packet contents. Things like:
  - The source IP
  - The destination IP
  - The packet size
  - Anything which could be observed from outside of the packet.
- Your flow logs can be configured to log valid traffic, invalid traffic, or both
- You can have flow logs sourced from a different VPC compared to the VPC where your Flow Logs are. However, the other VPC must be peered via VPC Peering and under your account via AWS Organizations.
- You can customize your logs by tagging them.
- Once you create a Flow Log, you cannot change its config. You must make a new one.
- Not all IP traffic is monitored under VPC Flow Logs. The following is a list of things that are ignored by Flow Logs:
  - Query requests for instance metadata
  - DHCP traffic
  - Query requests to the AWS DNS server
  
  ### AWS Global Accelerator:
- AWS Global Accelerator accelerates connectivity to improve performance and availability for users. Global Accelerator sits on top of the AWS backbone and directs traffic to optimal endpoints worldwide. By default, Global Accelerator provides you two static IP addresses that you can make use of.
- Global Accelerator helps reduce the number of hops to get to your AWS resources. Your users just need to make it to an edge location and once there, everything will remain internal to the AWS global network. Normally, it takes many networks to reach the application in full and paths to and from the application may vary. With each hop, there is risk involved either in security or in failure.

![Screen Shot 2020-06-21 at 5 50 02 PM](https://user-images.githubusercontent.com/13093517/85235996-aa0cbc00-b3e7-11ea-9e85-039f0ba6e770.png)

- In summary, Global Accelerator is a fast/reliable pipeline between user and application. 
- It's like going on a trip (web traffic) and stopping to ask for directions in possibly unsafe parts of town (multiple networks are visited which can increase security risks) as opposed to having a GPS (global accelerator) that leads you directly where you want to go (endpoint) without having to make unnecessary stops.
- It can be confused with Cloudfront, but CloudFront is a cache for content stemming from a distant origin server.
- While CloudFront simply caches static content to the closest AWS Point Of Presence (POP) location, Global accelerator will use the same Amazon POP to accept initial requests and routes them directly to the services. 
- Route53's latency based routing might also appear similar to Global Accelerator, but Route 53 is for simply helping choose which region for the user to use. Route53 has nothing to do with actually providing a fast network path.
- Global Accelerator also provides fast regional failover.

## Simple Queuing Service (SQS)

### SQS の概要:
 SQSはウェブベースのサービスであり、メッセージキューにアクセスすることができる。システムのデカップリングやAWSリソースの水平スケーリングに役立つ。

### SQS の詳細:
- The point behind SQS is to decouple work across systems. This way, downstream services in a system can perform work when they are ready to rather than when upstream services feed them data.
- In a hypothetical AWS environment running without SQS, *Application A* would pass *Application B* data regardless if Application B was ready to receive the info. With SQS however, there is an intermediary step where the data is stored temporarily in a buffer. It waits there until Application B pulls the temporarily stored data. SQS is not a push-based service so it is necessary for SQS to work in tandem with another service that queries it for information.
- There are two types of SQS queues; **standard** and **FIFO**. Standard queues may be received out of order based on message size or however else the SQS queues decide to optimize. FIFO queues guarantees that the order of messages that went into the queue is the same as the order of messages that leave it.
- Standard SQS queues guarantee that a message is delivered at least once and because of this, it is possible on occasion that a message might be delivered more than once due to the asynchronous and highly distributed architecture. With standard queues, you have a nearly unlimited number of transactions per second.
- FIFO SQS queues guarantee exactly-once processing and is limited to 300 transactions per second.
- Messages in the queue can be kept there from one minute to 14 days and the default retention period is 4 days.
- Visibility timeouts in SQS are the mechanism in which messages marked for delivery from the queue are given a time frame to be fully received by a reader. This is done by temporarily making them invisible to other readers. If the message is not fully processed within the time limit, the message becomes visible again. This is another way in which messages can be duplicated. If you want to reduce the chance of duplication, increase the visibility timeout. 
- The visibility timeout maximum is 12 hours.
- Always remember that the messages in the SQS queue will continue to exist even after the EC2 instance has processed it, until you delete that message. You have to ensure that you delete the message after processing to prevent the message from being received and processed again once the visibility timeout expires.
- An SQS queue can contain an unlimited number of messages. 
- You cannot set a priority to the individual items in the SQS queue. If priority of messaging matters, create two separate SQS queues. The SQS queues for the priority message can be polled first by the EC2 Instances and once completed, the messages from the second queue can be processed next.

### SQS Polling:
- Polling is the means in which you query SQS for messages or work. Amazon SQS provides short-polling and long-polling to receive messages from a queue. By default, queues use short polling. 
- **SQS long-polling**: This polling technique will only return from the queue once a message is there, regardless if the queue is currently full or empty. This way, the reader needs to wait either for the timeout set or for a message to finally arrive. SQS long polling doesn't return a response until a message arrives in the queue, reducing your overall cost over time. 
- **SQS short-polling**: This polling technique will return immediately with either a message that’s already stored in the queue or empty-handed. 
- The ReceiveMessageWaitTimeSeconds is the queue attribute that determines whether you are using Short or Long polling. By default, its value is zero which means it is using short-polling. If it is set to a value greater than zero, then it is long-polling.
- Every time you poll the queue, you incur a charge. So thoughtfully deciding on a polling strategy that fits your use case is important.

## Simple Workflow Service (SWF)

### SWF の概要:
SWFは、分散したアプリケーション・コンポーネント間の作業を簡単に調整できるウェブ・サービスだ。SWFには、メディア処理、ウェブアプリのバックエンド、ビジネスプロセスのワークフロー、分析パイプラインなど、さまざまな使用例がある。

### SWF の詳細:
- SWF is a way of coordinating tasks between application and people. It is a service that combines digital and human-oriented workflows.
- An example of a human-oriented workflow is the process in which Amazon warehouse workers find and ship your item as part of your Amazon order.
- SWF provides a task-oriented API and ensures a task is assigned only once and is never duplicated. Using Amazon warehouse workers as an example again, this would make sense. Amazon wouldn’t want to send you the same item twice as they'd lose money.
- The SWF pipeline is composed of three different worker applications that help to bring a job to completion:
  - SWF Actors are workers that trigger the beginning of a workflow.
  - SWF Deciders are workers that control the flow of the workflow once it's been started.
  - SWF Activity Workers are the workers that actually carry out the task to completion.
- With SWF, workflow executions can last up to one year compared to the 14 days maximum retention period for SQS.

## Simple Notification Service (SNS)

### SNS の概要:
Simple Notification Serviceはプッシュ型のメッセージングサービスで、特定のトピックに関する情報を希望する購読者にカスタムメッセージを発行するための、拡張性、柔軟性、コスト効率の高い方法を提供します。

### SNS の詳細:
- SNS is mainly used to send alarms or alerts.
- SNS provides topics for high-throughput, push-based, many-to-many messaging. 
- Using Amazon SNS topics, your publisher systems can fan out messages to a large number of subscriber endpoints for parallel processing, including Amazon SQS queues, AWS Lambda functions, and HTTP/S webhooks. Additionally, SNS can be used to fan out notifications to end users using mobile push, SMS, and email. 
- You can send these push notifications to Apple, Google, Fire OS, and Windows devices.
- SNS allows you to group multiple recipients using topics. A topic is an access point for allowing recipients to dynamically subscribe for identical copies of the same notification.
- One topic can support deliveries to multiple endpoint types. When you publish to a topic, SNS appropriately formats copies of that message to send to whichever kind of device.
- To prevent messages being lost, messages are stored redundantly across multiple AZs.
- There is no long or short polling involved with SNS due to the instantaneous pushing of messages
- SNS has flexible message delivery over multiple transport protocols and has a simple API.

## Kinesis 

### Kinesis の概要:
Amazon Kinesisを使用すると、リアルタイムのストリーミングデータを簡単に収集、処理、分析できるため、タイムリーな洞察を得て、新しい情報に迅速に対応できます。Amazon Kinesisを使用すると、機械学習、分析、その他のアプリケーションのために、ビデオ、オーディオ、アプリケーションログ、ウェブサイトのクリックストリーム、IoT遠隔測定データなどのリアルタイムデータを取り込むことができます。Amazon Kinesisを使用すると、すべてのデータが収集されるまで処理を開始するのを待つ必要がなく、データが到着するとすぐに処理して分析し、即座に対応することができます。

### Kinesis の詳細:
- Amazon Kinesis makes it easy to load and analyze the large volumes of data entering AWS.
- Kinesis is used for processing real-time data streams (data that is generated continuously) from devices constantly sending data into AWS so that said data can be collected and analyzed.
- It is a fully managed service that automatically scales to match the throughput of your data and requires no ongoing administration. It can also batch, compress, and encrypt the data before loading it, minimizing the amount of storage used at the destination and increasing security.
- There are three different types of Kinesis:
  - Kinesis Streams
    - Kinesis Streams works where the data producers stream their data into Kinesis Streams which can retain the data from one day up until 7 days. Once inside 
      Kinesis Streams, the data is contained within shards.
    - Kinesis Streams can continuously capture and store terabytes of data per hour from hundreds of thousands of sources such as website clickstreams, financial 
      transactions, social media feeds, IT logs, and location-tracking events. For example: purchase requests from a large online store like Amazon, stock prices, Netflix 
      content, Twitch content, online gaming data, Uber positioning and directions, etc.
      
  - Kinesis Firehose
    - Amazon Kinesis Firehose is the easiest way to load streaming data into data stores and analytics tools. When data is streamed into Kinesis Firehose, there is no 
      persistent storage there to hold onto it. The data has to be analyzed as it comes in so it's optional to have Lambda functions inside your Kinesis Firehose. Once 
      processed, you send the data elsewhere.
    - Kinesis Firehose can capture, transform, and load streaming data into Amazon S3, Amazon Redshift, Amazon Elasticsearch Service, and Splunk, enabling near real-time 
      analytics with existing business intelligence tools and dashboards you’re already using today.
      
  - Kinesis Analytics
    - Kinesis Analytics works with both Kinesis Streams and Kinesis Firehose and can analyze data on the fly. The data within Kinesis Analytics also gets sent elsewhere once 
      it is finished processing. It analyzes your data inside of the Kinesis service itself.

- Partition keys are used with Kinesis so you can organize data by shard. This way, input from a particular device can be assigned a key that will limit its destination to a specific shard.
- Partition keys are useful if you would like to maintain order within your shard.
- Consumers, or the EC2 instances that read from Kinesis Streams, can go inside the shards to analyze what is in there. Once finished analyzing or parsing the data, the consumers can then pass on the data to a number of places for storage like a DB or S3.
- The total capacity of a Kinesis stream is the sum of data within its constituent shards.
- You can always increase the write capacity assigned to your shard table.

## Lambda

### Lambda の概要:
AWS Lambdaを使えば、サーバーのプロビジョニングや管理をすることなくコードを実行できる。利用したコンピュート時間に対してのみ支払いが発生します。Lambdaを使えば、事実上あらゆるタイプのアプリケーションやバックエンド・サービスのコードを、すべてゼロ管理で実行できます。コードをアップロードすると、Lambdaがコードの実行と高可用性でのスケーリングに必要なすべての処理を行います。AWSの他のサービスから自動的にトリガーされるようにコードを設定したり、Webやモバイルアプリから直接呼び出すこともできます。

### Lambda の詳細:
- Lambda is a compute service where you upload your code as a function and AWS provisions the necessary details underneath the function so that the function executes successfully. 
- AWS Lambda is the ultimate abstraction layer. You only worry about code, AWS does everything else.
- Lambda supports Go, Python, C#, PowerShell, Node.js, and Java
- Each Lambda function maps to one request. Lambda scales horizontally automatically.
- Lambda is priced on the number of requests and the first one million are free. Each million afterwards is $0.20.
- Lambda is also priced on the runtime of your code, rounded up to the nearest 100mb, and the amount of memory your code allocates.
- Lambda works globally.
- Lambda functions can trigger other Lambda functions.
- You can use Lambda as an event-driven service that executes based on changes in your AWS ecosystem.
- You can also use Lambda as a handler in response to HTTP events via API calls over the AWS SDK or API Gateway.

![Screen Shot 2020-06-30 at 9 19 33 AM](https://user-images.githubusercontent.com/13093517/86130894-df35a000-bab2-11ea-9908-acbe3e8d4824.png)

- When you create or update Lambda functions that use environment variables, AWS Lambda encrypts them using the AWS Key Management Service. When your Lambda function is invoked, those values are decrypted and made available to the Lambda code.
- The first time you create or update Lambda functions that use environment variables in a region, a default service key is created for you automatically within AWS KMS. This key is used to encrypt environment variables. However, if you wish to use encryption helpers and use KMS to encrypt environment variables after your Lambda function is created, you must create your own AWS KMS key and choose it instead of the default key. 
- To enable your Lambda function to access resources inside a private VPC, you must provide additional VPC-specific configuration information that includes VPC subnet IDs and security group IDs. AWS Lambda uses this information to set up elastic network interfaces (ENIs) that enable your function to connect securely to other resources within a private VPC.

- AWS X-Ray allows you to debug your Lambda function in case of unexpected behavior.


### Lambda@Edge:
- You can use Lambda@Edge to allow your Lambda functions to customize the content that CloudFront delivers.
- It adds compute capacity to your CloudFront edge locations and allows you to execute the functions in AWS locations closer to your application's viewers. The functions run in response to CloudFront events, without provisioning or managing servers. You can use Lambda functions to change CloudFront requests and responses at the following points:
  - After CloudFront receives a request from a viewer (viewer request)
  - Before CloudFront forwards the request to the origin (origin request)
  - After CloudFront receives the response from the origin (origin response)
  - Before CloudFront forwards the response to the viewer (viewer response)
  
![Screen Shot 2020-06-30 at 9 27 48 AM](https://user-images.githubusercontent.com/13093517/86131713-fc1ea300-bab3-11ea-8190-1d13128bee92.png)

- You'd use Lambda@Edge to simplify and reduce origin infrastructure.


## API Gateway

### API Gateway の概要:
API Gateway は開発者向けのフルマネージドサービスで、API 全体の構築、公開、管理、セキュリティ確保を容易にします。AWS Management Consoleを数回クリックするだけで、EC2上で動作するワークロードやAWS Lambda上で動作するコード、あるいはWebアプリケーションなど、アプリケーションがバックエンドのサービスからデータやビジネスロジック、機能にアクセスするための「フロントドア」として機能するAPIを作成できる。

### API Gateway の詳細:
- Amazon API Gateway handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls, including traffic management, authorization and access control, monitoring, and API version management.
- Amazon API Gateway has no minimum fees or startup costs. You pay only for the API calls you receive and the amount of data transferred out.
- API Gateway does the following for your APIs:
  - Exposes HTTP(S) endpoints for RESTful functionality
  - Uses serverless functionality to connect to Lambda & DynamoDB
  - Can send each API endpoint to a different target
  - Runs cheaply and efficiently
  - Scales readily and effortlessly
  - Can throttle requests to prevent attacks
  - Track and control usage via an API key
  - Can be version controlled
  - Can be connected to CloudWatch for monitoring and observability
- Since API Gateway can function with AWS Lambda, you can run your APIs and code without needing to maintain servers.
- Amazon API Gateway provides throttling at multiple levels including global and by a service call.
  - In software, a throttling process, or a throttling controller as it is sometimes called, is a process responsible for regulating the rate at which application processing is conducted, either statically or dynamically.
  - Throttling limits can be set for standard rates and bursts. For example, API owners can set a rate limit of 1,000 requests per second for a specific method in their REST APIs, and also configure Amazon API Gateway to handle a burst of 2,000 requests per second for a few seconds. 
  - Amazon API Gateway tracks the number of requests per second. Any requests over the limit will receive a 429 HTTP response. The client SDKs generated by Amazon API Gateway retry calls automatically when met with this response.
- You can add caching to API calls by provisioning an Amazon API Gateway cache and specifying its size in gigabytes. The cache is provisioned for a specific stage of your APIs. This improves performance and reduces the traffic sent to your back end. Cache settings allow you to control the way the cache key is built and the time-to-live (TTL) of the data stored for each method. Amazon API Gateway also exposes management APIs that help you invalidate the cache for each stage.
- You can enable API caching for improving latency and reducing I/O for your endpoint.
- When caching for a particular API stage (version controlled version), you cache responses for a particular TTL in seconds.
- API Gateway supports AWS Certificate Manager and can make use of free TLS/SSL certificates.
- With API Gateway, there are two kinds of API calls:
  - Calls to the API Gateway API to create, modify, delete, or deploy REST APIs. These are logged in CloudTrail.
  - API calls set up by the developers to deliver their custom functionality: These are not logged in CloudTrail.


### Cross Origin Resource Sharing:
- In computing, the same-origin policy is an important concept where a web browser permits scripts contained in one page to access data from another page, but only if both pages have the same origin.
- This behavior is enforced by browsers, but is ignored by tools like cURL and PostMan.
- Cross-origin resource sharing (CORS) is one way the server at the origin can relax the same-origin policy. CORS allows sharing of restricted resources like fonts to be requested from another domain outside the original domain of where the first resource was shared from.
- CORS defines a way for client web applications that are loaded in one domain to interact with resources in a different domain. With CORS support, you can build rich client-side web applications with Amazon S3 and selectively allow cross-origin access to your Amazon S3 resources.
- If you ever come across an error that mentions that an origin policy cannot be read at the remote resource, then you need to enable CORS on API Gateway.
- CORS is enforced on the client (web browser) side.
- A common example of this issue is if you are using a site with Javascript/AJAX for multiple domains under API Gateway. You would need to ensure that CORS is enabled.
- CORS does not prevent XSS attacks, but does protect against CSRF attacks. What it does is controls who can use the data served by your endpoint. So if you have a weather website with callbacks to an API that checks the forecast, you could stop someone from writing a website that serves JavaScript calls into your API when they navigate to your website.
- When someone attempts the malicious calls, your browser will read the CORS headers and it will not allow the request to take place thus protecting you from the attack.

## CloudFormation

### CloudFormation の概要:
CloudFormationは、クラウドベースの環境全体をプロビジョニングするための自動化ツールだ。これはTerraformに似ていて、アプリケーションのセットアップで何をしたいのか（X台のYタイプのウェブサーバーとバックエンドのZタイプのDBなど）をコード化する。マークアップで欲しいものを記述するだけで、AWSに実際のプロビジョニング作業をさせることができる。

### CloudFormation の詳細:
- The main use case for CloudFormation is for advanced setups and production environments as it is complex and has many robust features.
- CloudFormation templates can be used to create, update, and delete infrastructure.
- The templates are written in YAML or JSON
- A full CloudFormation setup is called a stack.
- Once a template is created, AWS will make the corresponding stack. This is the living and active representation of said template. One template can create an infinite number of stacks.
- The *Resources* field is the only mandatory field when creating a CloudFormation template
- Rollback triggers allow you to monitor the creation of the stack as it's built. If an error occurs, you can trigger a rollback as the name implies.
- <a href="https://aws.amazon.com/quickstart/?quickstart-all.sort-by=item.additionalFields.updateDate&quickstart-all.sort-order=desc">AWS Quick Starts is composed of many high-quality CloudFormation stacks designed by AWS engineers.</a>
- An example template that would spin up an EC2 instance:

![Screen Shot 2020-07-01 at 8 44 52 AM](https://user-images.githubusercontent.com/13093517/86245210-27b69180-bb77-11ea-8dff-3d663957a8e2.png)

- For any Logical Resources in the stack, CloudFormation will make a corresponding Physical Resources in your AWS account. It is CloudFormation’s job to keep the logical and physical resources in sync.
- A template can be updated and then used to update the same stack.


## ElasticBeanstalk

### ElasticBeanstalk の概要:
ElasticBeanstalkは、既存のアプリケーションをクラウドにデプロイすることで、プロビジョニング・プロセスをスクリプト化するもう一つの方法だ。ElasticBeanstalkは、クラウドについてほとんど知識がなく、コードをデプロイする最もシンプルな方法を求めている開発者を対象としている。

### ElasticBeanstalk の詳細:
- Just upload your application and ElasticBeanstalk will take care of the underlying infrastructure.
- ElasticBeanstalk has capacity provisioning, meaning you can use it with autoscaling from the get-go.
ElasticBeanstalk applies updates to your application by having a duplicate ready with the already updated version. This duplicate is then swapped with the original. This is done as a preventative measure in case your updated application fails. If the app does fail, ElasticBeanstalk will switch back to the original copy with the older version and there will be no downtime experienced by the users who are using your application. 
- You can use ElasticBeanstalk to even host Docker as Elastic Beanstalk supports the deployment of web applications from containers. With Docker containers, you can define your own runtime environment, your own platform, programming language, and any application dependencies (such as package managers or tools) that aren't supported by other platforms. ElasticBeanstalk makes it easy to deploy Docker as Docker containers are already self-contained and include all the configuration information and software required to run. 

## AWS Organizations

### AWS Organizations の概要:
AWS Organizationsは、複数のAWSアカウントを1つの組織に統合し、作成・一元管理できるアカウント管理サービスです。

### AWS Organizations の詳細:
- Best practices is to use the root account to manage billing only with separate accounts used to deploy resources.
- The point of AWS Organizations is to deploy permissions to the separate accounts underneath the root account and have those policies trickle down. AWS Organizations helps you centrally govern your environment as you grow and scale your workloads on AWS. 
- You can use organizational units (OUs) to group similar accounts together to administer as a single unit. This greatly simplifies the management of your accounts. 
- You can attach a policy-based control to an OU, and all accounts within the OU automatically inherit the policy. So if your company's developers all have their own sandbox AWS account, they can be treated as a single unit and be restricted by the same policies.
- With AWS Organizations, we can enable or disable services using Service Control Policies (SCPs) broadly on organizational units or more specifically on individual accounts
- Use SCPs with AWS Organizations to establish access controls so that all IAM principals (users and roles) adhere to them. With SCPs, you can specify *Conditions*, *Resources*, and *NotAction* to deny access across accounts in your organization or organizational unit. For example, you can use SCPs to restrict access to specific AWS Regions, or prevent deleting common resources, such as an IAM role used for your central administrators.

## Miscellaneous

The following section includes services, features, and techniques that may appear on the exam. They are also extremely useful to know as an engineer using AWS. If the following items do appear on the exam, they will not be tested in detail. You'll just have to know what the meaning is behind the name. It is a great idea to learn each item in depth for your career's benefit, but it is not necessary for the exam.

### Amazon Cognitoとは何か? 
- Before discussing Amazon Cognito, it is first important to understand what Web Identity Federation is. Web Identity Federation lets you give your users access to AWS resources after they have successfully authenticated into a web-based identity provider such as Facebook, Google, Amazon, etc. Following a successful login into these services, the user is provided an auth code from the identity provider which can be used to gain temporary AWS credentials.
- Amazon Cognito is the Amazon service that provides Web Identity Federation. You don’t need to write the code that tells users to sign in for Facebook or sign in for Google on your application. Cognito does that already for you out of the box.
- Once authenticated into an identity provider (say with Facebook as an example), the provider supplies an auth token. This auth token is then supplied to Cognito which responds with limited access to your AWS environment. You dictate how limited you would like this access to be in the IAM role.
- Cognito's job is broker between your app and legitimate authenticators.
- *Cognito User Pools* are user directories that are used for sign-up and sign-in functionality on your application. Successful authentication generates a JSON web token. Remember user pools to be user based. It handles registration, recovery, and authentication.
- *Cognito Identity Pools* are used to allow users temp access to direct AWS Services like S3 or DynamoDB. Identity pools actually go in and grant you the IAM role.
- SAML-based authentication can be used to allow AWS Management Console login for non-IAM users.
- In particular, you can use Microsoft Active Directory which implements Security Assertion Markup Language (SAML) as well.
- You can use Amazon Cognito to deliver temporary, limited-privilege credentials to your application so that your users can access AWS resources. 
- Amazon Cognito identity pools support both authenticated and unauthenticated identities. 
- You can retrieve a unique Amazon Cognito identifier (identity ID) for your end user immediately if you're allowing unauthenticated users or after you've set the login tokens in the credentials provider if you're authenticating users.
- When you need to easily add authentication to your mobile and desktop app, think Amazon Cognito.

### AWS Resource Access Managerとは何か?
- AWS Resource Access Manager (RAM)は、任意のAWSアカウントまたはAWS組織内でAWSリソースを簡単かつ安全に共有できるサービスです。AWSトランジットゲートウェイ、サブネット、AWSライセンスマネージャ設定、Amazon Route 53 ResolverルールリソースをRAMで共有できます。
- 多くの組織は、管理または請求の分離を作成し、AWS Organizationsサービスの一部としてエラーの影響を制限するために、複数のアカウントを使用しています。
- RAMは、複数のアカウントで重複したリソースを作成する必要性を排除し、所有するすべてのアカウントでそれらのリソースを管理する運用オーバーヘッドを削減します。
- マルチアカウント環境で一元的にリソースを作成し、RAMを使用して、リソース共有の作成、リソースの指定、アカウントの指定の3つの簡単なステップで、アカウント間でリソースを共有することができます。
- RAMは追加料金なしでご利用いただけます。

### Athenaとは何か?
- Athenaはインタラクティブなクエリサービスで、標準SQLコマンドを使ってS3からデータを照会することができる。これは一般的な開発者にとってプログラム的なクエリに有益である。サーバーレスで、プロビジョニングが不要で、クエリごととスキャンしたTBごとに支払いが発生する。Athenaを使うことで、S3をSQLでサポートされたデータベースに変えることができる。
- 使用例
  - ELKスタックの代替または補足としてS3バケットにダンプされるクエリログ
  - S3に定期的に入るデータに基づいてビジネスレポートを実行するためのクエリの設定
  - クリックストリームデータに対してクエリーを実行し、顧客の行動をさらに把握する。

### AWS Macieとは何か?
- マッキーを理解するためには、PII（個人識別情報）を理解することが重要である：
  - 個人の身元を確認するために使用され、悪用される可能性のある個人情報。
  - 例 社会保障番号、電話番号、自宅住所、電子メールアドレス、D.O.B、パスポート番号など。
- Amazon Macieは、Amazon S3に保存された機密データを自動的に検出、分類、保護することで、データ損失を防ぐMLを活用したセキュリティサービスです。Amazon Macieは、機械学習を使用して、個人を特定できる情報（PII）や知的財産などの機密データを認識し、ビジネス価値を割り当て、このデータがどこに保存され、組織内でどのように使用されているかを可視化します。
- 検出されたデータは、Macieのダッシュボード、アラート、またはレポートによって通知されます。
- また、MacieはCloudTrailのログを分析し、機密データに誰がアクセスしたかを確認することができます。
- Macieはデータアクセスアクティビティに異常がないかを継続的に監視し、不正アクセスや不注意によるデータ漏えいのリスクを検出するとアラートを配信します。
- Macieには、機密データに誤って設定されたグローバルアクセス許可を検出する機能、ソースコード内のAPIキーのアップロードを検出する機能、機密性の高い顧客データがコンプライアンス基準を満たす方法で保存およびアクセスされていることを検証する機能があります。

### AWS KMSとは何か?
- AWS Key Management Service（AWS KMS）は、データの暗号化に使用する暗号鍵を簡単に作成・管理できるマネージドサービスです。AWS KMSで作成するマスターキーは、FIPS 140-2検証済みの暗号モジュールによって保護されます。
- AWS KMSは、お客様が管理する暗号鍵でデータを暗号化する他のほとんどのAWSサービスと統合されています。また、AWS KMSはAWS CloudTrailと統合されており、暗号化キーの使用ログを提供することで、監査、規制、コンプライアンスのニーズを満たすことができます。
- ディスクに保存する前にすべてのデータを暗号化するために、KMS APIを使用するようにアプリケーションを構成することができます。

### AWS Secrets Managerとは何か?
- AWS Secrets Managerは、シークレットの管理を容易にするAWSサービス。
- シークレットには、データベースの認証情報、パスワード、サードパーティのAPIキー、さらには任意のテキストを使用できます。Secrets Managerコンソール、Secrets Managerコマンドラインインターフェイス（CLI）、Secrets Manager APIとSDKを使用することで、これらのシークレットを一元的に保存し、アクセスを制御することができます。
- 以前は、データベースから情報を取得するカスタムアプリケーションを作成する場合、通常はデータベースにアクセスするための認証情報（シークレット）をアプリケーションに直接埋め込む必要がありました。クレデンシャルをローテーションするとき、新しいクレデンシャルを作成するだけでなく、もっと多くのことをしなければなりませんでした。新しいクレデンシャルを使うためにアプリケーションをアップデートする時間を投資しなければならなかった。そして、更新したアプリケーションを配布しなければならなかった。クレデンシャルを共有する複数のアプリケーションがあり、そのうちの1つを更新し損ねると、アプリケーションは壊れてしまう。
- このリスクのために、多くのお客様はクレデンシャルを定期的にローテーションしないことを選択しました。
- Secrets Managerは、コードにハードコードされたクレデンシャル（パスワードを含む）をSecrets ManagerへのAPIコールで置き換え、シークレットをプログラムで取得することを可能にします。
- これにより、誰かがあなたのコードを調査しても、秘密が漏れることはありません。
- また、あなたが指定したスケジュールに従って、シークレットマネージャーが自動的にシークレットをローテーションするように設定することもできます。これにより、長期的なシークレットを短期的なシークレットに置き換えることができ、漏洩のリスクを大幅に減らすことができます。

### AWS STSとは何か?
- AWS Security Token Service (AWS STS)は、AWSリソースへのアクセスを制御できる一時的なセキュリティ認証情報を作成し、信頼できるユーザーに提供するために使用できるサービスです。
- 一時的なセキュリティ認証情報は、IAM ユーザーが使用できる長期的なアクセスキーの認証情報とほぼ同じように機能します。
- 一時的なセキュリティ認証情報は、その名の通り短期的なものです。数分から数時間持続するように設定できます。クレデンシャルの有効期限が切れると、AWSはそのクレデンシャルを認識しなくなり、そのクレデンシャルを使って行われたAPIリクエストからのアクセスを一切許可しなくなる。

### OpsWorksとは何か?
- AWS OpsWorksは、ChefとPuppetのマネージドインスタンスを提供する構成管理サービスだ。ChefとPuppetは、コードを使用してサーバーの構成を自動化できる自動化プラットフォームです。
- OpsWorksを使用すると、ChefとPuppetを使用して、Amazon EC2インスタンスまたはオンプレミスのコンピュート環境全体でサーバーを構成、デプロイ、管理する方法を自動化できる。
- OpsWorksには、AWS Opsworks for Chef Automate、AWS OpsWorks for Puppet Enterprise、AWS OpsWorks Stacksの3つの製品がある。
- AWS OpsWorks Stacksでは、AWSとオンプレミス上のアプリケーションとサーバーを管理できる。OpsWorks Stacksを使用すると、ロードバランシング、データベース、アプリケーションサーバーなどの異なるレイヤーを含むスタックとしてアプリケーションをモデル化できます。
- OpsWorks Stacksは、各レイヤーにAmazon EC2インスタンスをデプロイして構成したり、Amazon RDSデータベースなどの他のリソースに接続したりできるほど複雑です。

### Elastic Transcoderとは何か?
- クラウド上のメディア・トランスコーダー。基本的には、メディアファイルを元のフォーマットから、電話、タブレット、PCなど、指定されたメディアフォーマットに変換するサービスです。
- 様々なメディアタイプに対応しているため、出来上がりの品質は信頼できる。
- Elastic Transcoderでは、トランスコード作業の分単位と、完成した作業の解像度ごとに料金を支払います。

### AWS Directory Serviceとは何か?
- AWS Directory Serviceは、Amazon Cloud DirectoryとMicrosoft Active Directory（AD）を他のAWSサービスで使用するための複数の方法を提供します。- ディレクトリは、ユーザー、グループ、デバイスに関する情報を格納し、管理者は情報やリソースへのアクセスを管理するために使用する。
- AWS Directory Serviceは、既存のMicrosoft ADやLDAP（Lightweight Directory Access Protocol）対応のアプリケーションをクラウドで使用したい顧客に対して、複数のディレクトリの選択肢を提供する。また、ユーザー、グループ、デバイス、アクセスを管理するためのディレクトリを必要とする開発者にも、同様の選択肢を提供する。

### IoT Coreとは何か?
- AWS IoT Coreは、コネクテッドデバイスがクラウドアプリケーションや他のデバイスと簡単かつ安全にやり取りできるようにするマネージドクラウドサービスです。
- AWS IoT Coreは、さまざまな種類のコネクテッドデバイスやロケーション間でセキュアな通信とデータ処理を提供するため、IoTアプリケーションを簡単に構築できます。

### AWS WorkSpacesとは何か?
- Amazon WorkSpacesは、管理された安全なDaaS（Desktop-as-a-Service）ソリューションです。Amazon WorkSpacesを使用すると、WindowsまたはLinuxデスクトップをわずか数分でプロビジョニングし、世界中の従業員に数千台のデスクトップを提供できるように迅速に拡張できます。
- Amazon WorkSpacesは、ハードウェアの在庫、OSのバージョンとパッチ、仮想デスクトップインフラ（VDI）の管理の複雑さを解消し、デスクトップ提供戦略の簡素化を支援します。
- Amazon WorkSpacesを使用すれば、ユーザーは、いつでもどこでも、サポートされているデバイスからアクセスできる、高速で応答性の高いデスクトップを選択できます。

### AWS Fargateとは何か?
- AWS Fargateはコンテナ用のサーバーレスコンピュートエンジンだ。
- Fargateの起動タイプでは、バックエンドのインフラをプロビジョニング、管理することなく、コンテナ化されたアプリケーションを実行できる。タスク定義を登録するだけで、Fargateがコンテナを起動してくれる。
- Amazon Elastic Container Service（ECS）とAmazon Elastic Kubernetes Service（EKS）の両方で動作する。
- Fargateを使えば、アプリケーションの構築に集中することができます。サーバーのプロビジョニングと管理の必要性をなくし、アプリケーションごとにリソースを指定して支払うことができ、設計によるアプリケーションの分離によってセキュリティを向上させます。

### Amazon Elastic Container Serviceとは何か?
- Amazon Elastic Container Service（Amazon ECS）は、完全に管理されたコンテナ・オーケストレーション・サービスです。
- Amazon ECSを利用することで、独自のクラスタ管理インフラをインストール、運用、スケールする必要がなくなります。シンプルなAPIコールで、コンテナ対応アプリケーションの起動と停止、クラスタの完全な状態の照会、セキュリティグループ、Elastic Load Balancing、EBSボリューム、IAMロールなどのおなじみの多くの機能へのアクセスが可能です。
- Amazon ECSを使用して、リソースニーズと可用性要件に基づいてクラスタ全体にコンテナを配置するスケジュールを立てることができます。また、ビジネスやアプリケーション固有の要件を満たすために、独自のスケジューラやサードパーティのスケジューラを統合することもできます。
- コンテナ用のサーバーレス・コンピュートであるAWS Fargateを使用してECSクラスタを実行することもできます。Fargateは、サーバーのプロビジョニングと管理の必要性を排除し、アプリケーションごとにリソースを指定して支払うことができ、設計によるアプリケーションの分離によってセキュリティを向上させます。

### Amazon Elastic Kubernetes Serviceとは何か?
- Amazon Elastic Kubernetes Service（Amazon EKS）はフルマネージドのKubernetesサービスです。EKSはアップストリームのKubernetesを実行し、Kubernetes準拠の認定を受けているため、コミュニティからのオープンソースツールのすべての利点を活用できます。また、コードをリファクタリングすることなく、標準的なKubernetesアプリケーションを簡単にEKSに移行できます。
- Kubernetesは、コンテナ化されたアプリケーションを大規模にデプロイおよび管理できるオープンソースソフトウェアです。Kubernetesはコンテナを論理的なグループ分けして管理・発見し、EC2インスタンスのクラスタ上に起動します。Kubernetesを使用すると、マイクロサービス、バッチ処理ワーカー、サービスとしてのプラットフォーム（PaaS）などのコンテナ化されたアプリケーションを、オンプレミスとクラウドで同じツールセットを使用して実行できます。
- Amazon EKSは、APIサーバーとバックエンドの永続化レイヤーを含むKubernetesのコントロールプレーンを、複数のAWSアベイラビリティゾーンにわたってプロビジョニングおよびスケーリングし、高可用性と耐障害性を実現します。Amazon EKSは、不健全なコントロールプレーンノードを自動的に検出して交換し、コントロールプレーンにパッチを適用します。
- Amazon EKSがなければ、Kubernetesのコントロールプレーンとワーカーノードのクラスタの両方を自分で実行する必要があります。Amazon EKSを使用すると、EKSコンソール、CLI、またはAPIで1つのコマンドを使用してワーカーノードをプロビジョニングし、AWSが可用性の高いセキュアな構成でKubernetesコントロールプレーンのプロビジョニング、スケーリング、管理を行います。これにより、Kubernetesを実行するための運用負荷が大幅に軽減され、AWSインフラストラクチャの管理ではなく、アプリケーションの構築に集中できるようになる。
- コンテナ用のサーバーレス・コンピュートであるAWS Fargateを使ってEKSを実行できる。Fargateは、サーバーのプロビジョニングと管理の必要性を排除し、アプリケーションごとにリソースを指定して支払うことができ、設計によるアプリケーションの分離によってセキュリティを向上させます。
- Amazon EKSは多くのAWSサービスと統合されており、アプリケーションにスケーラビリティとセキュリティを提供します。これらのサービスには、負荷分散のためのElastic Load Balancing、認証のためのIAM、分離のためのAmazon VPC、ロギングのためのAWS CloudTrailが含まれます。

### What does pilot light mean?
- パイロット・ライトという言葉は、クラウド上で環境の最小バージョンが常に稼働しているディザスタリカバリ・シナリオを説明するためによく使われる。
- パイロット・ライトのアイデアは、ガス・ヒーターに由来するアナロジーだ。ガスストーブでは、常に点いている小さな炎が炉全体に素早く点火し、家を暖めることができる。このシナリオは、バックアップとリストアのシナリオに似ている。
- 例えば、AWSを使えば、システムの最も重要なコアエレメントをAWSで構成し実行することで、パイロットランプを維持することができる。リカバリーの時期が来たら、常に稼働している重要なコアを中心に、フルスケールの本番環境を迅速にプロビジョニングすることができる。

### What are Blue-Green deployments?
- デプロイメントを自動化する際の課題の1つは、テストの最終段階から本番環境へのカットオーバーです。通常、ダウンタイムを最小限に抑えるために、これを迅速に行う必要があります。
- Blue-Greenデプロイメントアプローチは、可能な限り同一の2つの本番環境を確保することでこれを実現します。いつでもそのうちの1つ（例ではブルーとします）が本番環境です。ソフトウェアの新しいリリースを準備する際、最終段階のテストをグリーン環境で行います。ソフトウェアがグリーン環境で動作するようになったら、ルーターを切り替えて、すべての着信リクエストがグリーン環境に行くようにします。
- ブルー・グリーン・デプロイメントでは、ロールバックも迅速に行える。何か問題が発生したら、ルーターをブルー環境に戻す。
- CloudFormationとCodeDeploy（AWS版のJenkins）はどちらもこのデプロイ手法をサポートしている。
- 
### Amazon Data Lifecycle Managerとは何か?
- Amazon Data Lifecycle Manager（Amazon DLM）を使用して、Amazon EBSボリュームをバックアップするために取得したスナップショットの作成、保持、および削除を自動化できます。
- スナップショット管理を自動化すると、以下のことが可能になります：
  - 定期的なバックアップスケジュールを実施することで、貴重なデータを保護します。
  - 監査人または内部コンプライアンスによって要求されたバックアップを保持します。
  - 古いバックアップを削除することで、ストレージコストを削減します。
- Amazon DLM を使用すると、EBS スナップショットの取得を覚えておく必要がなくなるため、エンジニアの認識負荷が軽減されます。

### Route Origin Authorizationとは何か?
- オンプレミスのネットワークからパブリックIPv4アドレス範囲の一部または全部をAWSアカウントに持ってくることができる。アドレス範囲は引き続きお客様の所有ですが、AWSがインターネット上で広告します。アドレス範囲をAWSに持ってくると、アドレスプールとしてアカウントに表示されます。
- その後、アドレスプールからElastic IPアドレスを作成し、EC2インスタンス、NATゲートウェイ、ネットワークロードバランサーなどのAWSリソースで使用することができます。これは「BYOIP（Bring Your Own IP Addresses）」とも呼ばれる。
- あなただけがあなたのAWSアカウントにあなたのアドレス範囲をもたらすことができるようにするために、あなたはアドレス範囲を宣伝するためにアマゾンを承認し、あなたがアドレス範囲を所有していることを証明するものを提供する必要があります。
- ROAの利点は、パートナーや顧客がIPアドレスのホワイトリストを変更することなく、既存のアプリケーションをAWSに移行できることだ。 

### Amazon MQとは何か?
- Amazon MQはマネージド・メッセージ・ブローカー・サービスで、クラウド上でメッセージ・ブローカーのセットアップと運用を簡単に行うことができる。
- このサービスは、サービスやアプリをオンプレミスからクラウドに移行する際に使用され、Amazon SQSとは異なる。
- Amazon MQは、高可用性とメッセージの耐久性をサポートするためにAmazon EFSによってバックアップされた耐久性に最適化されたブローカーと、低レイテンシーと高スループットを必要とする大容量アプリケーションをサポートするためにAmazon EBSによってバックアップされたスループットに最適化されたブローカーをサポートしています。
- アプリケーションのメッセージングコードを書き換える必要がないため、あらゆるメッセージブローカーからAmazon MQに簡単に移行できます。
- Amazon MQは、オンプレミスであれクラウドであれ、メッセージブローカーを自社で管理しており、アプリケーションのメッセージングコードを書き換えることなく完全に管理されたクラウドサービスに移行したいと考えている企業のIT担当者、開発者、アーキテクトに適しています。

### AWS Configとは何か?
- AWS Configは、AWSリソースの構成の評価、監査、および評価を可能にするサービスです。Configは、AWSリソースの構成を継続的に監視、記録し、記録された構成と目的の構成との評価を自動化することができます。
- Configを使用すると、AWSリソース間の構成と関係の変更を確認し、リソースの構成履歴を詳細に調べ、社内ガイドラインで指定された構成に対する全体的なコンプライアンスを判断できます。これにより、コンプライアンス監査、セキュリティ分析、変更管理、および運用上のトラブルシューティングを簡素化できます。
- AWS Configでは以下のことが可能です： -        
  - AWS リソースの構成を評価し、必要な設定を行う。-         
  - AWS アカウントに関連付けられているサポートされているリソースの現在の構成のスナップショットを取得する。-        
  - アカウントに存在する 1 つ以上のリソースの構成を取得します。-       
  - 1つまたは複数のリソースの過去の構成を取得します。-     
  - リソースが作成、変更、削除されるたびに通知を受け取る。    
  - リソース間の関係を表示する。例えば、特定のセキュリティグループを使用するすべてのリソースを検索したい場合など。
