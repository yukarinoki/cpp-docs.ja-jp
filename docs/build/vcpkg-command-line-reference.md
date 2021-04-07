---
title: vcpkg コマンドライン リファレンス
description: Windows、macOS、Linux 上で vcpkg のコマンドライン オプションを使用する方法について説明します。
ms.date: 12/17/2020
ms.topic: reference
ms.technology: cpp-ide
ms.openlocfilehash: 22210f3ee80050890d0b71fcc26461372e77e11e
ms.sourcegitcommit: 82a0d23b04d0776c00209d885689cbc5be36d3b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "106099626"
---
# <a name="vcpkg-command-line-reference"></a>vcpkg コマンドライン リファレンス

vcpkg で使用できるコマンドのクイック リファレンス。

## <a name="commands"></a>コマンド

| command | 説明 |
|--|--|
| **`vcpkg search [pat]`** | インストールに使用できるパッケージを検索します |
| **`vcpkg install <pkg>...`** | パッケージをインストールします |
| **`vcpkg remove <pkg>...`** | パッケージをアンインストールします |
| **`vcpkg remove --outdated`** | 古いパッケージをアンインストールします |
| **`vcpkg list`** | インストールされているパッケージをリストします |
| **`vcpkg update`** | 更新対象のパッケージのリストを表示します |
| **`vcpkg upgrade`** | すべての古いパッケージをリビルドします。 |
| **`vcpkg hash <file> [alg]`** | 特定のアルゴリズム (既定では SHA512) を使用して、ファイルをハッシュします |
| **`vcpkg integrate install`** | インストールされているパッケージをユーザー全体で使用できるようにします。 初回使用時は管理特権が必要です |
| **`vcpkg integrate remove`** | ユーザー全体の統合を削除します |
| **`vcpkg integrate project`** | 個々の VS プロジェクト使用のために参照する NuGet パッケージを生成します |
| **`vcpkg export <pkg>... [opt]...`** | パッケージをエクスポートします |
| **`vcpkg edit <pkg>`** | 編集対象のポートを開きます (既定の 'コード' %EDITOR% を使用) |
| **`vcpkg create <pkg> <url> [archivename]`** | 新しいパッケージを作成します |
| **`vcpkg cache`** | キャッシュされたコンパイル済みのパッケージをリストします |
| **`vcpkg version`** | バージョン情報を表示します |
| **`vcpkg contact --survey`** | フィードバックを送信する連絡先の情報を表示します。 |

## <a name="options"></a>オプション

| オプション | 説明 |
|--|--|
| **`--triplet <t>`** | ターゲット アーキテクチャのトリプレットを指定します。 (既定値: `%VCPKG_DEFAULT_TRIPLET%`。 **`vcpkg help triplet`** も参照してください) |
| **`--vcpkg-root <path>`** | vcpkg ルート ディレクトリを指定します (既定値: `%VCPKG_ROOT%`) |

## <a name="see-also"></a>関連項目

[vcpkg: Windows、Linux、および macOS 用の C++ パッケージ マネージャー](./vcpkg.md)\
[GitHub 上の vcpkg](https://github.com/Microsoft/vcpkg)\
[vcpkg をインストールする](install-vcpkg.md)\
[vcpkg を統合する](integrate-vcpkg.md)\
[vcpkg を使用してライブラリを管理する](manage-libraries-with-vcpkg.md)\
[クイック スタート](https://github.com/microsoft/vcpkg/blob/master/docs/README.md)\
[よく寄せられる質問](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
