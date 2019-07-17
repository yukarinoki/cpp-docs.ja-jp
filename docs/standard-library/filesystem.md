---
title: '&lt;filesystem&gt;'
ms.date: 11/04/2016
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::recursive_directory_iterator
- filesystem/std::experimental::filesystem::path
- filesystem/std::experimental::filesystem::filesystem_error
- filesystem/std::experimental::filesystem::directory_iterator
- <filesystem>
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
ms.openlocfilehash: a44fc3c6c6a37c20e1e1c294929ae3cb15cece58
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240693"
---
# <a name="ltfilesystemgt"></a>&lt;filesystem&gt;

パス、ファイル、およびディレクトリに関する情報の操作や取得を行うクラスおよび関数にアクセスするには、ヘッダー &lt;filesystem> をインクルードします。

## <a name="syntax"></a>構文

```cpp
#include <experimental/filesystem> // C++-standard header file name
#include <filesystem> // Microsoft-specific implementation header file name
using namespace std::experimental::filesystem::v1;
```

> [!IMPORTANT]
> Visual Studio 2017 のリリース以降、 \<filesystem > ヘッダーが、まだ C++ 標準。 C++Visual Studio 2017 (MSVC v141) の実装で、最終ドラフト標準はで見つかった[ISO/IEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)します。

このヘッダーは、ホスト オペレーティング システムの 2 つの広範なクラスのいずれかのファイル システムをサポートしています。Microsoft Windows と Posix します。

ほとんどの機能が両方のオペレーティング システムに共通していますが、このドキュメントではそれらの相違点について説明します。 例えば:

- Windows は、c: や \\\network_name などの複数のルート名をサポートします。 ファイル システムはツリーのフォレストで構成され、それぞれのツリーが持つ c:\ や \\\network_name\\ などの独自のルート ディレクトリと現在のディレクトリから相対パス名 (絶対パス名ではないもの) が生成されます。

- Posix は、ルート名のない単一のツリー、単一のルート ディレクトリ /、および単一の現在のディレクトリをサポートします。

もう 1 つの大きな違いは、パス名のネイティブな表現です。

- Windows では、UTF-16 (文字ごとに 1 つまたは 2 つの要素) としてエンコードされた wchar_t の null 終端シーケンスが使用されます。

- Posix では、UTF-8 (文字ごとに 1 つ以上の要素) としてエンコードされた char の null 終端シーケンスが使用されます。

- クラス パスのオブジェクトは、パス名をネイティブ形式で格納しますが、この格納形式といくつかの外部形式の間の簡単な変換をサポートします。

- オペレーティング システムで優先されるようにエンコードされた char の null 終端シーケンス。

- UTF-8 としてエンコードされた char の null 終端シーケンス。

- オペレーティング システムで優先されるようにエンコードされた wchar_t の null 終端シーケンス。

- UTF-16 としてエンコードされた char16_t の null 終端シーケンス。

- UTF-32 としてエンコードされた char32_t の null 終端シーケンス。

必要に応じて、1 つまたは複数の `codecvt` ファセットを使用することによって、これらの表現の相互変換が実施されます。 特定のロケール オブジェクトが指定されなかった場合は、これらのファセットがグローバル ロケールから取得されます。

もう 1 つの相違点は、オペレーティング システムで指定可能なファイルまたはディレクトリのアクセス許可の詳細です。

1. Windows は、ファイルが読み取り専用なのか書き込み可能なのかという、ディレクトリには意味のない属性を記録します。

1. Posix は、ファイルが所有者、所有者のグループ、またはすべてのユーザーに加えて、その他のいくつかのアクセス許可によって、読み取り、書き込み、または実行 (ディレクトリの場合はスキャン) が可能かどうかを記録します。

両方のシステムに共通しているのは、ルート名に到達するまでのパス名に適用される構造です。 パス名 c:/abc/xyz/def.ext の場合:

- ルート名は c: です。

- ルート ディレクトリは / です。

- ルート パスは c:/ です。

- 相対パスは abc/xyz/def.ext です。

- 親パスは c:/abc/xyz です。

- ファイル名は def.ext です。

- ステムは def です。

- 拡張子は .ext です。

小さな相違点は、パス名内のディレクトリのシーケンスの **優先区切り記号**です。 両方のオペレーティング システムでスラッシュ / を記述できますが、一部のコンテキストでは、Windows で円記号 \\ が優先されます。

最後に、パス オブジェクトの重要な特徴として、ヘッダー \<fstream> で定義されたクラスで filename 引数が必要な場合はパス オブジェクトを使用することができます。

詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|||
|-|-|
|[directory_entry クラス](../standard-library/directory-entry-class.md)|`directory_iterator` または `recursive_directory_iterator` で返されるオブジェクトを記述します。また、パスが含まれます。|
|[directory_iterator クラス](../standard-library/directory-iterator-class.md)|ファイル システム ディレクトリのファイル名をシーケンス処理する入力反復子を表します。|
|[filesystem_error クラス](../standard-library/filesystem-error-class.md)|低レベル システム オーバーフローをレポートするためにスローされる例外のための基底クラス。|
|[path クラス](../standard-library/path-class.md)|ファイル名として使用するのに適したテンプレート型 `String` のオブジェクトを格納するクラスを定義します。|
|[recursive_directory_iterator クラス](../standard-library/recursive-directory-iterator-class.md)|ファイル システム ディレクトリのファイル名をシーケンス処理する入力反復子を表します。 反復子はサブディレクトリに下りることもできます。|
|[file_status クラス](../standard-library/file-status-class.md)|`file_type`をラップします。|

### <a name="structs"></a>構造体

|||
|-|-|
|[space_info 構造体](../standard-library/space-info-structure.md)|ボリュームに関する情報を保持します。|

## <a name="functions"></a>関数

[\<filesystem> 関数](../standard-library/filesystem-functions.md)

## <a name="operators"></a>演算子

[\<filesystem> 演算子](../standard-library/filesystem-operators.md)

## <a name="enumerations"></a>列挙

|||
|-|-|
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|[copy_file](../standard-library/filesystem-functions.md#copy_file) と共に使用され、コピー先ファイルが既に存在する場合の動作を決定する列挙体です。|
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|[copy_file](../standard-library/filesystem-functions.md#copy_file) と共に使用され、コピー先ファイルが既に存在する場合の動作を決定する列挙体です。|
|[directory_options](../standard-library/filesystem-enumerations.md#directory_options)|ディレクトリ反復子のオプションを指定する列挙体。|
|[file_type](../standard-library/filesystem-enumerations.md#file_type)|ファイルの種類の列挙型。|
|[perm_options](../standard-library/filesystem-enumerations.md#perm_options)||
|[perms](../standard-library/filesystem-enumerations.md#perms)|アクセス許可とアクセス許可に対するオプションを伝達するために使用されるビットマスク型|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
