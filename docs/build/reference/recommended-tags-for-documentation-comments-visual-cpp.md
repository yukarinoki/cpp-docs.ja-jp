---
title: ドキュメントコメント用の推奨タグC++ (ドキュメントコメント)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 4e0937b79012f65ba136e18ac81f014be23688f8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168864"
---
# <a name="recommended-tags-for-documentation-comments"></a>ドキュメント コメントとして推奨されるタグ

MSVC コンパイラは、コード内のドキュメントコメントを処理し、コンパイル単位ごとに .xdc ファイルを作成します。 xdcmake は、.xdc ファイルを .xml ファイルに処理します。 .xml ファイルを加工してドキュメントを作成することは、自分のサイトで実行する必要がある項目です。

型や型メンバーなどのコンストラクトでタグが処理されます。

タグは型やメンバーの直前に置く必要があります。

> [!NOTE]
>  ドキュメント コメントは名前空間に適用できず、プロパティやイベントのアウトオブライン定義に置くことはできません。ドキュメント コメントは、クラス内宣言に置く必要があります。

コンパイラは、有効な XML のタグをすべて処理します。 次のタグによって、ユーザー ドキュメントで一般的に使用される機能が与えられます。

||||
|-|-|-|
|[\<c>](c-visual-cpp.md)|[\<code>](code-visual-cpp.md)|[\<example>](example-visual-cpp.md)|
|[\<exception>](exception-visual-cpp.md)1|[\<include>](include-visual-cpp.md)1|[\<list>](list-visual-cpp.md)|
|[\<para>](para-visual-cpp.md)|[\<param>](param-visual-cpp.md)1|[\<paramref>](paramref-visual-cpp.md)1|
|[\<permission>](permission-visual-cpp.md)1|[\<remarks>](remarks-visual-cpp.md)|[\<returns>](returns-visual-cpp.md)|
|[\<see>](see-visual-cpp.md)1|[\<seealso>](seealso-visual-cpp.md)1|[\<summary>](summary-visual-cpp.md)|
|[\<value>](value-visual-cpp.md)|||

1. コンパイラによって構文が検証されます。

現在のリリースでは、MSVC コンパイラは、他の Visual Studio コンパイラでサポートされているタグ `<paramref>`をサポートしていません。 Visual C++ では、将来のリリースで `<paramref>` がサポートされる可能性があります。

## <a name="see-also"></a>参照

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
