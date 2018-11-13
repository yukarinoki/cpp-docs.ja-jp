---
title: ドキュメント コメントとして推奨されるタグ (Visual C++)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 251baedbf37901a58b34b66b7a10bbdcf5d66557
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564191"
---
# <a name="recommended-tags-for-documentation-comments-visual-c"></a>ドキュメント コメントとして推奨されるタグ (Visual C++)

Visual C++ コンパイラは、コードのドキュメント コメントを処理し、コンパイル単位ごとに .xdc ファイルを作成します。xdcmake.exe によって .xdc ファイルが .xml ファイルに変換されます。 .xml ファイルを加工してドキュメントを作成することは、自分のサイトで実行する必要がある項目です。

型や型メンバーなどのコンストラクトでタグが処理されます。

タグは型やメンバーの直前に置く必要があります。

> [!NOTE]
>  ドキュメント コメントは名前空間に適用できず、プロパティやイベントのアウトオブライン定義に置くことはできません。ドキュメント コメントは、クラス内宣言に置く必要があります。

コンパイラは、有効な XML のタグをすべて処理します。 次のタグによって、ユーザー ドキュメントで一般的に使用される機能が与えられます。

||||
|-|-|-|
|[\<c>](../ide/c-visual-cpp.md)|[\<code>](../ide/code-visual-cpp.md)|[\<example>](../ide/example-visual-cpp.md)|
|[\<exception>](../ide/exception-visual-cpp.md)1|[\<include>](../ide/include-visual-cpp.md)1|[\<list>](../ide/list-visual-cpp.md)|
|[\<para>](../ide/para-visual-cpp.md)|[\<param>](../ide/param-visual-cpp.md)1|[\<paramref>](../ide/paramref-visual-cpp.md)1|
|[\<permission>](../ide/permission-visual-cpp.md)1|[\<remarks>](../ide/remarks-visual-cpp.md)|[\<returns>](../ide/returns-visual-cpp.md)|
|[\<see>](../ide/see-visual-cpp.md)1|[\<seealso>](../ide/seealso-visual-cpp.md)1|[\<summary>](../ide/summary-visual-cpp.md)|
|[\<value>](../ide/value-visual-cpp.md)|||

1. コンパイラによって構文が検証されます。

現行リリースの Visual C++ コンパイラでは、他の Visual Studio コンパイラでサポートされているタグ、`<paramref>` がサポートされていません。 Visual C++ では、将来のリリースで `<paramref>` がサポートされる可能性があります。

## <a name="see-also"></a>参照

[XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)