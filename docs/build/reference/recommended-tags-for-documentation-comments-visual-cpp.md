---
title: ドキュメント コメントの推奨タグ (C++ ドキュメント コメント)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 1648d0eb019a3aad25641d7f6a7edd1ba26acf7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336169"
---
# <a name="recommended-tags-for-documentation-comments"></a>ドキュメント コメントとして推奨されるタグ

MSVC コンパイラは、コード内のドキュメント コメントを処理し、コンパイルおよび各コンパイル用の .xdc ファイルを作成し、xdcmake.exe は .xdc ファイルを .xml ファイルに処理します。 .xml ファイルを加工してドキュメントを作成することは、自分のサイトで実行する必要がある項目です。

型や型メンバーなどのコンストラクトでタグが処理されます。

タグは型やメンバーの直前に置く必要があります。

> [!NOTE]
> ドキュメント コメントは名前空間に適用できず、プロパティやイベントのアウトオブライン定義に置くことはできません。ドキュメント コメントは、クラス内宣言に置く必要があります。

コンパイラは、有効な XML のタグをすべて処理します。 次のタグによって、ユーザー ドキュメントで一般的に使用される機能が与えられます。

||||
|-|-|-|
|[\<c>](c-visual-cpp.md)|[\<コード>](code-visual-cpp.md)|[\<>例](example-visual-cpp.md)|
|例外>1 [ \< ](exception-visual-cpp.md)|>1[を含む\<](include-visual-cpp.md)|[\<リスト>](list-visual-cpp.md)|
|[\<パラ>](para-visual-cpp.md)|パラム>1 [ \< ](param-visual-cpp.md)|パラムレフ>1 [ \< ](paramref-visual-cpp.md)|
|アクセス許可>1 [ \< ](permission-visual-cpp.md)|[\<>の発言](remarks-visual-cpp.md)|[\<>を返す](returns-visual-cpp.md)|
|>1[を参照してください。 \< ](see-visual-cpp.md)|参照も>1 [ \< ](seealso-visual-cpp.md)|[\<概要>](summary-visual-cpp.md)|
|[\<値>](value-visual-cpp.md)|||

1. コンパイラによって構文が検証されます。

現在のリリースでは、MSVC コンパイラは、他`<paramref>`の Visual Studio コンパイラでサポートされているタグをサポートしていません。 Visual C++ では、将来のリリースで `<paramref>` がサポートされる可能性があります。

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
