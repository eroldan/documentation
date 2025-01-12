---
code_lang: php
code_lang_weight: 40
kind: documentation
title: PHP 互換性要件
type: multi-code-lang
---

## ASM の機能サポート

PHP ライブラリでは、指定されたトレーサーのバージョンで、以下の ASM 機能がサポートされています。

| ASM の機能                   | PHP トレーサーの最小バージョン |
| -------------------------------- | ----------------------------|
| Threat Detection | 0.84.0     |
| Threat Protection  | 0.86.0   |
| オープンソースソフトウェア (OSS) の脆弱性管理 | 非対応 |
| コードレベルの脆弱性管理 (ベータ版) | 非対応|

PHP でサポートされるすべての ASM 機能を得るためのトレーサーの最小バージョンは 0.86.0 です。


<div class="alert alert-info">サポートされていない機能のサポート追加を希望される場合は、お知らせください！<a href="https://forms.gle/gHrxGQMEnAobukfn7">この短いフォーム</a>に必要事項を記入して、詳細を送信してください。</div>

### サポートされるデプロイメントタイプ
|タイプ | 脅威検知のサポート | OSSの脆弱性管理のサポート |
| ---           |   ---             |           ----            |
| Docker        | {{< X >}}         |                           |
| Kubernetes    | {{< X >}}         |                           | 
| AWS ECS       | {{< X >}}         |                           |
| AWS Fargate   |                   |                           |
| AWS Lambda    |                   |                           |   

## 言語とフレームワークの互換性

<div class="alert alert-info">
<strong>注:</strong>
PHP 5.x はバージョン 0.75.0 まで完全にサポートされています。現在はメンテナンスモードに移行しており、2023 年 12 月 31 日までセキュリティや重要なバグの修正でサポートされています。

<br>
<br>

もし、アプリケーションで PHP 5.x バージョンを使用していて、ビジネスニーズにとって重要な機能要求がある場合は、<a href="https://www.datadoghq.com/support/">Datadog サポート</a>にご連絡ください。

PHP は<a href="https://www.php.net/supported-versions">公式にサポートされているバージョン</a>、特に 7.4、8.0、8.1 を使用することが推奨されています。
</div>

| PHP バージョン    | サポートレベル                         | パッケージバージョン |
|:---------------|:--------------------------------------|:----------------|
| 8.2.x          | 一般提供                  | > `0.82.0+`     |
| 8.1.x          | 一般提供                  | > `0.66.0+`     |
| 8.0.x          | 一般提供                  | > `0.52.0+`     |
| 7.4.x          | 一般提供                  | All             |
| 7.3.x          | 一般提供                  | All             |
| 7.2.x          | 一般提供                  | All             |
| 7.1.x          | 一般提供                  | All             |
| 7.0.x          | 一般提供                  | All             |
| 5.6.x          | メンテナンス (2023 年 12 月 31 日まで) | All             |
| 5.5.x          | メンテナンス (2023 年 12 月 31 日まで) | All             |
| 5.4.x          | メンテナンス (2023 年 12 月 31 日まで) | All             |

PHP ASM は以下の SAPI に対応しています。

| SAPI           | サポートの種類    |
|:---------------|:----------------|
| apache2handler | 完全対応 |
| cli            | 完全対応 |
| fpm-fcgi       | 完全対応 |
| cgi-fcgi       | 完全対応 |

## 対応プロセッサアーキテクチャー

PHP ASM は以下のアーキテクチャに対応しています。

| プロセッサアーキテクチャー                   | サポートレベル         | パッケージバージョン                        |
| ------------------------------------------|-----------------------|----------------------------------------|
| Linux GNU amd64 (`x86-64-linux-gnu`)      | GA                    | All                                    |
| Linux MUSL amd64 (`x86-64-linux-musl`)    | GA                    | All                                    |
| Linux GNU arm64 (`aarch64-linux-gnu`)     | GA                    | > `0.78.0`                             |
| Linux MUSL arm64 (`aarch64-linux-musl`)   | GA                    | > `0.78.0`                             |

Datadog PHP ライブラリは、以下のアーキテクチャの PHP バージョン 7.0 以降をサポートしています。

- Linux (GNU) x86-64
- Alpine Linux (musl) x86-64

ライブラリはすべての PHP フレームワークの使用をサポートし、またフレームワークなしの使用も可能です。


### Web フレームワークの互換性

- 攻撃元の HTTP リクエストの詳細
- HTTP リクエスト用のタグ (ステータスコード、メソッドなど)
- アプリケーション内の攻撃フローを確認するための分散トレーシング

##### ASM の機能に関する備考
- **Vulnerability Management for OSS** はサポートされていません
- **Vulnerability Management for Code-level** はサポートされていません

以下のフレームワークは ASM によって直接インスツルメンテーションされませんが、ランタイムインスツルメンテーションによって間接的にサポートされます。

| フレームワーク                | バージョン    | 脅威検知のサポートの有無 | 脅威保護のサポートの有無 |
| ------------------------ | ----------- | --------------- | ---------------------------------------------- |
| CakePHP       | 2.x       |  {{< X >}} | {{< X >}} |
| CodeIgniter   | 2.x       |  {{< X >}} | {{< X >}} |
| FuelPHP       | 1.1        |  {{< X >}} | {{< X >}} |
| Laravel       | 4.2、5.x、6.x        | {{< X >}} | {{< X >}} |
| Laravel 8     | 8.x (トレーサー 0.52.0+) | {{< X >}} | {{< X >}} |
| Lumen         | 1.9-2.29    |  {{< X >}} | {{< X >}} |
| Magento       |  3.8+       |  {{< X >}} | {{< X >}} |
| Neos Flow     |  3.0.x      |  {{< X >}} | {{< X >}} |
| Phalcon       | 3.1+        |  {{< X >}} | {{< X >}} |
| Roadrunner    | 3.1+        |  {{< X >}} | {{< X >}} |
| Slim          | 3.1+        |  {{< X >}} | {{< X >}} |
| Symfony 3     | 3.1+        |  {{< X >}} | {{< X >}} |
| Symfony 4     | 3.1+        |  {{< X >}} | {{< X >}} |
| Symfony 5     | 3.1+        |  {{< X >}} | {{< X >}} |
| Wordpress     | 3.1+        |  {{< X >}} | {{< X >}} |
| Yii           | 3.1+        |  {{< X >}} | {{< X >}} |
| Zend          | 3.1+        |  {{< X >}} | {{< X >}} |
| Symfony 3     | 3.1+        |  {{< X >}} | {{< X >}} |


### データストアの互換性

**データストアのトレーシングでは以下の確認が可能です**

- SQL 攻撃の検知
- クエリ情報 (サニタイジングされたクエリ文字列など)
- エラーとスタックトレースの取得

##### ASM の機能に関する備考
- **Vulnerability Management for OSS** はサポートされていません
- **Vulnerability Management for Code-level** はサポートされていません
- **脅威保護** は HTTP リクエスト (input) レイヤーでも機能するため、下表に掲載されていなくても、デフォルトですべてのデータベースで機能します。

| フレームワーク         | バージョン | 脅威検知のサポートの有無    | 脅威保護のサポートの有無|
|-------------------|-----------------|-----------------|---------------|
| Amazon RDS        | サポートされているすべての PHP | {{< X >}}  |   {{< X >}} | 
| Eloquent       | Laravel 対応バージョン | {{< X >}} | {{< X >}} |
| Memcached        | サポートされているすべての PHP |   {{< X >}}    | {{< X >}} |
| MySQLi        | サポートされているすべての PHP | {{< X >}} | {{< X >}} |
| PDO        | サポートされているすべての PHP| {{< X >}}| {{< X >}} |
| PHPRedis        | 3、4、5 |   {{< X >}}    | {{< X >}} |
| Predis        | 1.1 | {{< X >}} |   {{< X >}}    |

[1]: /ja/tracing/trace_collection/compatibility/php/
[2]: /ja/agent/remote_config/#enabling-remote-configuration