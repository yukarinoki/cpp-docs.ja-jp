---
title: ドキュメントコメント用の推奨タグ (C++ ドキュメントコメント)
ms.date: 11/04/2016
ms.assetid: 6548e798-5235-4a38-9482-bdc7b88f40a9
ms.openlocfilehash: 9f41e450215e2bce02dbaf66910fc2fc1a131a99
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836856"
---
# <a name="recommended-tags-for-documentation-comments"></a>ドキュメント コメントとして推奨されるタグ

MSVC コンパイラは、コード内のドキュメントコメントを処理し、コンパイル単位ごとに .xdc ファイルを作成します。また、xdcmake.exe は、.xdc ファイルを .xml ファイルに処理します。 .xml ファイルを加工してドキュメントを作成することは、自分のサイトで実行する必要がある項目です。

型や型メンバーなどのコンストラクトでタグが処理されます。

タグは型やメンバーの直前に置く必要があります。

> [!NOTE]
> ドキュメント コメントは名前空間に適用できず、プロパティやイベントのアウトオブライン定義に置くことはできません。ドキュメント コメントは、クラス内宣言に置く必要があります。

コンパイラは、有効な XML のタグをすべて処理します。 次のタグによって、ユーザー ドキュメントで一般的に使用される機能が与えられます。

[`<c>`](c-visual-cpp.md)
[`<code>`](code-visual-cpp.md)
[`<example>`](example-visual-cpp.md)
[`<exception>`](exception-visual-cpp.md)<sup>1</sup> 
 1 [`<include>`](include-visual-cpp.md)<sup>1</sup> 
 [`<list>`](list-visual-cpp.md) 1 
 [`<para>`](para-visual-cpp.md) 
 [`<param>`](param-visual-cpp.md)<sup>1</sup> 
 1 [`<paramref>`](paramref-visual-cpp.md)<sup>1</sup> 
 1 [`<permission>`](permission-visual-cpp.md)<sup>1</sup> 
 [`<remarks>`](remarks-visual-cpp.md) 1 
 [`<returns>`](returns-visual-cpp.md) 
 [`<see>`](see-visual-cpp.md)<sup>1</sup> 
 1 [`<seealso>`](seealso-visual-cpp.md)<sup>1</sup>
[`<summary>`](summary-visual-cpp.md)
[`<value>`](value-visual-cpp.md)

1. コンパイラによって構文が検証されます。

現在のリリースでは、MSVC コンパイラは `<paramref>` 、他の Visual Studio コンパイラでサポートされているタグをサポートしていません。 Visual C++ では、将来のリリースで `<paramref>` がサポートされる可能性があります。

## <a name="see-also"></a>関連項目

[XML に関するドキュメント](xml-documentation-visual-cpp.md)
