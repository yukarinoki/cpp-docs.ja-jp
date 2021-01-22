---
title: '&lt;filesystem&gt;'
description: 標準 C++ ライブラリのヘッダーに含まれるクラス、関数、および型について説明し filesystem ます。
ms.date: 01/15/2021
f1_keywords:
- <filesystem>
- filesystem/std::filesystem
- std::filesystem
- std::experimental::filesystem
no-loc:
- filesystem
- experimental
- char
- wchar_t
- char16_t
- char32_t
ms.openlocfilehash: 8dc81692c7c7dc467f3ab8e2ceb8cac19e004ab8
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667472"
---
# `filesystem`

`<filesystem>`パス、ファイル、およびディレクトリに関する情報を操作および取得するクラスおよび関数にアクセスするためのヘッダーを含めます。

## <a name="syntax"></a>Syntax

```cpp
#include <filesystem> // C++17 standard header file name
#include <experimental/filesystem> // Header file for pre-standard implementation
using namespace std::experimental::filesystem::v1;
```

> [!IMPORTANT]
> Visual Studio 2017 のリリースでは、 \<filesystem> ヘッダーはまだ C++ 標準ではありませんでした。 Visual Studio 2017 RTW の C++ では、 [ISO/IEC JTC 1/SC 22/WG 21 N4100](https://wg21.link/n4100)にある最終的なドラフト標準が実装されています。 Visual Studio 2017 バージョン15.7 以降では、新しい C++ 17 標準がサポートされてい \<filesystem> ます。
> これはまったく新しい実装であり、以前のバージョンと互換性がありません `std::experimental` 。 これは、シンボリックリンクのサポート、バグの修正、標準の必須動作の変更によって必要になりました。 現在、を含むは、 \<filesystem> 新しいと以前のを提供し `std::filesystem` `std::experimental::filesystem` ます。 \<experimental/filesystem>を含めると、以前の実装のみが提供され experimental ます。 この experimental 実装は、ライブラリの次の ABI リリースで削除される予定です。

このヘッダーは、2つの広範なホストオペレーティングシステム (Microsoft Windows と POSIX) のいずれかのファイルシステムをサポートしています。

ほとんどの機能が両方のオペレーティング システムに共通していますが、このドキュメントではそれらの相違点について説明します。 次に例を示します。

- Windows では、やなど、複数のルート名がサポートされてい `c:` `\\network_name` ます。 ファイルシステムはツリーのフォレストで構成されており、それぞれがやなどの独自のルートディレクトリを持ち、 `c:\` `\\network_name\` それぞれが独自の現在のディレクトリを持ち、相対パス名 (絶対パス名ではないもの) を完成させます。

- POSIX は、ルート名のない単一のツリー、単一のルートディレクトリ、および1つの現在のディレクトリをサポートしてい `/` ます。

もう 1 つの大きな違いは、パス名のネイティブな表現です。

- Windows では **`wchar_t`** 、utf-16 (各 acter に1つ以上の要素) としてエンコードされたの null 終端シーケンスを使用し char ます。

- POSIX では **`char`** 、utf-8 (各 acter に1つ以上の要素) としてエンコードされたの null 終端シーケンスを使用し char ます。

- クラスのオブジェクトは、 `path` パス名をネイティブ形式で格納しますが、この格納形式といくつかの外部形式の間の簡単な変換をサポートします。

  - オペレーティングシステムで優先されるようにエンコードされた、null で終わるのシーケンス **`char`** 。

  - **`char`** Utf-8 としてエンコードされた、null で終わるのシーケンス。

  - オペレーティングシステムで優先されるようにエンコードされた、null で終わるのシーケンス **`wchar_t`** 。

  - UTF-16 としてエンコードされたの null で終わるシーケンス **`char16_t`** 。

  - **`char32_t`** 32 utf-8 としてエンコードされた、null で終わるのシーケンス。

  必要に応じて、1 つまたは複数の `codecvt` ファセットを使用することによって、これらの表現の相互変換が実施されます。 特定のロケールオブジェクトが指定されていない場合、これらのファセットはグローバルロケールから取得されます。

もう 1 つの相違点は、オペレーティング システムで指定可能なファイルまたはディレクトリのアクセス許可の詳細です。

- Windows は、ファイルが読み取り専用であるか書き込み可能であるかを記録します。この属性は、ディレクトリに対して意味がありません。

- POSIX は、ファイルの読み取り、書き込み、または実行 (ディレクトリの場合はスキャン) が可能かどうかを記録します。 また、各操作を所有者、所有者のグループ、またはすべての人に許可し、他のいくつかのアクセス許可を許可するかどうかも指定します。

両方のシステムに共通しているのは、ルート名に到達するまでのパス名に適用される構造です。 パス名の場合 `c:/abc/xyz/def.ext` :

- ルート名は `c:` です。

- ルートディレクトリが `/` です。

- ルートパスが `c:/` です。

- 相対パスは `abc/xyz/def.ext` です。

- 親パスが `c:/abc/xyz` です。

- ファイル名が `def.ext` です。

- ステムは `def` です。

- 拡張機能は `.ext` です。

軽微な違いは、パス名にあるディレクトリのシーケンス間の推奨される区切り記号です。 どちらのオペレーティングシステムでもスラッシュを記述でき `/` ますが、一部のコンテキストでは円記号が優先さ `\` れます。 実装では、のデータメンバーに、優先する区切り記号が格納され `preferred_separator` `path` ます。

最後に、オブジェクトには `path` 重要な機能があります。ヘッダーに定義されているクラスで filename 引数が必要な場合は、それらを使用でき [\<fstream>](fstream.md) ます。

詳細とコード例については、「 [ファイルシステムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[`directory_entry` 講義](../standard-library/directory-entry-class.md)|またはによって返され、を含むオブジェクトを記述し `directory_iterator` `recursive_directory_iterator` `path` ます。|
|[`directory_iterator` 講義](../standard-library/directory-iterator-class.md)|ファイル システム ディレクトリのファイル名をシーケンス処理する入力反復子を表します。|
|[`filesystem_error` 講義](../standard-library/filesystem-error-class.md)|低レベル システム オーバーフローをレポートするためにスローされる例外のための基底クラス。|
|[`path` 講義](../standard-library/path-class.md)|ファイル名として使用するのに適したテンプレート型 `String` のオブジェクトを格納するクラスを定義します。|
|[`recursive_directory_iterator` 講義](../standard-library/recursive-directory-iterator-class.md)|ファイル システム ディレクトリのファイル名をシーケンス処理する入力反復子を表します。 反復子はサブディレクトリに下りることもできます。|
|[`file_status` 講義](../standard-library/file-status-class.md)|`file_type`をラップします。|

### <a name="structs"></a>構造体

|名前|説明|
|-|-|
|[`space_info` データ](../standard-library/space-info-structure.md)|ボリュームに関する情報を保持します。|

## <a name="functions"></a>機能

[\<filesystem> 関数](../standard-library/filesystem-functions.md)

## <a name="operators"></a>演算子

[\<filesystem> 通信](../standard-library/filesystem-operators.md)

## <a name="enumerations"></a>列挙型

|名前|説明|
|-|-|
|[`copy_options`](../standard-library/filesystem-enumerations.md#copy_options)|[copy_file](../standard-library/filesystem-functions.md#copy_file) と共に使用され、コピー先ファイルが既に存在する場合の動作を決定する列挙体です。|
|[`directory_options`](../standard-library/filesystem-enumerations.md#directory_options)|ディレクトリ反復子のオプションを指定する列挙体。|
|[`file_type`](../standard-library/filesystem-enumerations.md#file_type)|ファイルの種類の列挙型。|
|[`perm_options`](../standard-library/filesystem-enumerations.md#perm_options)| 関数のオプションを列挙 `permissions` します。 |
|[`perms`](../standard-library/filesystem-enumerations.md#perms)|アクセス許可とアクセス許可に対するオプションを伝達するために使用されるビットマスク型|

## <a name="see-also"></a>こちらもご覧ください

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)
