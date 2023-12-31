---
title: "About"
date: 2023-07-02T17:27:37+09:00
draft: false
---

最終更新日: 2023/07/03

# 基本情報
|  key  |  value  |
| ---- | ---- |
|  氏名  |  Shoichi Imamura（今村 翔一）|
|  居住地  |  東京  |

# スキル

- 言語
  - **Go**, **Ruby**, **TypeScript**, JavaScript
- フロントエンド
  - **React**, **Redux**, **Webpack**, \*React Native
- バックエンド
  - Gin, **Rails**, **gRPC**, OpenAPI, **REST**
- インフラストラクチャ
  - **AWS (Route53, ALB, EKS, ECR, EC2, RDS, ElastiCache, SNS, SQS, S3, IAM)**, Terraform, Kubernetes, Helm
- データベース
  - MySQL, Redis
- CI/CD
  - Github Actions, CircleCI, Datadog

**太字**はコアなスキルを表現します。
\* は実務経験のないものか、実務経験はあっても数年以上離れているスキルを表現します。

# 職務要約
Web・バックエンドを強みの中心としつつ、新規サービスの開発立ち上げから運用までの経験があります。実装だけでなく要件定義を始めとし、外部パートナー含む関係者とコミュニケーションをとり開発をリードしてきました。特に決済領域などで複雑なビジネスロジックや可用性・堅牢性の求められるシステムの開発に従事してきました。

主に以下の経験があります。

- 5年以上のGo・Ruby on Rails・Reactの開発
- フロントエンド・バックエンド・インフラの構築までのフルスタックな開発
- カードやファクタリングなどの決済領域のサービスの開発
- マイクロサービスの設計・開発
- 複数の新規サービスの開発

# 職務経歴
|  社名  |  期間  |
| ---- | ---- |
|  freee株式会社  |  2017/04~  |

## freee (2017.04 ~ )
|  プロジェクト  |  期間  |  主な経験  |
| ---- | ---- | ---- |
|  法人カード  |  2021/01~  |  マイクロサービスの新規開発・運用、グローバル開発  |
|  借り上げ社宅サービス  |  2020/02~2020/12  |  複雑な要件の設計・実装  |
|  請求書買取サービス  |  2019/04~2020/01  |  外部パートナーとの新規開発  |
|  証憑データ化サービス  |  2018/04~2019/03  |  サービスの新規開発  |
|  法人税申告サービス  |  2017/04~2018/03  |  既存サービスの開発  |

### 【freee】 法人カードの開発 2021/01~
| チーム構成 | 担当 | 使用技術 |
| --- | --- | --- |
| 4~名 (エンジニア2~, デザイナー1~, PdM1~) | 技術選定、仕様策定、バックエンド実装、フロントエンド実装、インフラ構築 | Go, Ruby, Rails, TypeScript, React |

法人向けのカードのシステムの開発です。このサービスはカードの発行を行う主体（イシュワー）として企業の与信を行い、カード利用時の与信確保（オーソリ）を行い、利用額に応じた請求を行います。
サービスやアーキテクチャの概要について[こちらの記事](https://developers.freee.co.jp/entry/freee-card-unlimited-overview)を執筆しました。

開発初期の2人のメンバーの1人としてサービスの設計からフロントエンド・バックエンド・インフラ構築含めて実装を担いました。マイクロサービスアーキテクチャを採用し、サービス間の通信や決済・請求・与信・権限管理・通知に関するサービスの設計と実装を進め、今のほとんどの機能の基礎となる部分を開発しました。

特にサービス間の非同期通信はメッセージの重複や喪失、処理順序を考慮し不整合が起こらないように設計しました。詳細については[こちらの記事](https://developers.freee.co.jp/entry/asynchronous-communication)に執筆しました。

また、サービスの特性上外部パートナーのシステムとの連携が多く、リトライ可否の判定や回数、間隔を調整できるクライアントを実装し、開発の標準化を進めました。
他には複数のチームで開発が進められるようにフィーチャーフラグのパッケージの実装もしました。

2023/07からはグローバルチームの立ち上げ時のメンバーとして英語で主なコミュニケーションを行っています。

主に取り組んだことは以下になります。

- マイクロサービスの設計・実装
  - 業務ドメインを分析し、サービスの境界の決定
  - Amazon SNS・SQSによるサービス間非同期通信の設計・実装
- 各サービスの設計・実装
  - クリーンアーキテクチャによる実装方針の言語化
  - カード管理・オーソリ・請求・与信・通知サービスの設計と実装
  - カード発行や本人確認、与信、請求などのバッチ処理の実装
  - 外部のパートナーのシステムとの連携
  - ロールに基づいたユーザーのアクセス制御
- 大規模リファクタリング・データ移行
  - 1事業所カード1枚の保持から複数枚に対応
  - 本人確認・反社チェックなどの申込手続きを他サービスと共通化
- 各サービスのインフラ構築
  - Amazon EKSによるkubernetesクラスタの構築
  - TerraformによるAWSリソースの追加
- グローバルチームでの開発
- 採用・新メンバーのオンボーディング

### 【freee】 借り上げ社宅サービスの開発 2020/02~2020/12
| チーム構成 | 担当 | 使用技術 |
| --- | --- | --- |
| 5名 (エンジニア3, デザイナー1, PdM1) | 技術選定、仕様策定、バックエンド実装、フロントエンド実装、インフラ構築 | Ruby, Rails, TypeScript, React |

従業員が探してきた賃貸物件を会社が借り、そこに従業員が住むという借上げ社宅制度を実現するシステムの開発です。開発初期のメンバーとして管理会社・企業・従業員・システム管理者向けの機能開発をしました。

PdM・UXと議論しながら、複雑な入居・更新・退去の流れを整理して仕様の決定に関わりました。従業員・管理会社・人事労務担当者・システム管理者向けの画面の機能開発を行いました。遷移する状態は40以上あったので仕様が複雑になる過程で、適宜データモデルを見直しリファクタリングしながら開発しました。

主に取り組んだことは以下になります。


- テックリードとしてサービス全体の設計やPdM, UXと仕様の策定
- Ruby, Railsを用いたバックエンドの設計・開発
- TypeScript, React, Reduxを用いたフロントエンドの設計・開発

### 【freee】 請求書買取サービスの開発 2019/04~2020/01
| チーム構成 | 担当 | 使用技術 |
| --- | --- | --- |
| 3~5名 (エンジニア1~3, デザイナー1, PdM1) | 技術選定、仕様策定、バックエンド実装、フロントエンド実装、インフラ構築 | Go, Ruby, Rails, TypeScript, React |

請求書ファイナンスとは、企業が保有する請求書をはじめとした売掛債権を売却（ファクタリング）することで、早期に資金化できるサービスです。開発初期は1人で設計・実装を行いました。また外部パートナーであるファクタリングサービスと連携するため、仕様や連携方法について調整も行いました。サービスや当時の働き方については[こちらのインタビュー記事](https://www.wantedly.com/companies/freee/post_articles/187040)に掲載されています。

Goを使った債権を管理し、外部パートナーとはREST APIで通信し、社内の会計サービスとはgRPCで通信します。[こちらの記事](https://speakerdeck.com/shoichiimamura/the-case-of-microservice-design-using-go)で設計や技術選択について執筆しています。

会計サービス側にはオファーできる債権を収集するバッチ処理と、ユーザー向けのフロントエンドの開発を行いました。アプリケーションはEKSで運用され、Helmチャートによるリソースの定義、TerraformによるAWSの各種リソースの設定も行いました。


- テックリードとしてサービス全体の設計やPdM, UXと仕様の策定
- Go, Ruby, Railsを用いたバックエンドの設計・開発
- TypeScript, React, Reduxを用いたフロントエンドの設計・開発

### 【freee】 証憑データ化サービスの開発 2018/04~2019/03
| チーム構成 | 担当 | 使用技術 |
| --- | --- | --- |
| 4名 (エンジニア3, PdM1) | 技術選定、仕様策定、バックエンド実装、フロントエンド実装、インフラ構築 | Go, Ruby, Rails, JavaScript, React |

領収書・レシートや通帳などの証憑をスキャン・アップロードすると1～2営業日以内に仕訳データ化し出力できるサービスの開発です。アップロードされた証憑を入力するオペレーター向けの業務アプリケーションが主な開発対象でした。データモデリングからオペレーターの認証機能や権限管理、各画面の実装を担いました。バックエンドは主にGoで、フロントエンドはJavaScript, Reactになります。kubernetesやTerraformによるAWSのリソースの定義・設定も行いました。

### 【freee】法人税申告サービスの開発 2017/04~2018/03
| チーム構成 | 担当 | 使用技術 |
| --- | --- | --- |
| 7名 (エンジニア5, デザイナー1, PdM1) | 技術選定、仕様策定、バックエンド実装、フロントエンド実装 | Ruby, Rails, JavaScript, React |

税理士が顧問先の企業の申告業務を行うためのシステムの開発です。バックエンドはRuby, RailsでフロントエンドはJavaScript, Reactでの開発でした。
特に複数の法人の申告を一括で行うための機能開発でデータモデリングからPdMとの仕様の策定まで幅広く行いました。

# 学歴
- 2017/03 筑波大学社会国際学群経済学類 卒業

# 資格
- 2023/02 TOEFL iBT 93点
- 2019/04 AWS Certified Solutions Architect - Associate 合格

