---
description: 詳細については、「Microsoft 固有の修飾子」を参照してください。
title: Microsoft 固有の修飾子
ms.date: 08/16/2018
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
ms.openlocfilehash: dd82bf22da99e864a7b4898da1a99a12c3ad3de4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161625"
---
# <a name="microsoft-specific-modifiers"></a>Microsoft 固有の修飾子

このセクションでは、次の領域での C++ への Microsoft 固有の拡張について説明します。

- [ベースとなるアドレス指定](based-addressing.md)(ポインターをベースとして使用し、他のポインターをオフセットできること)

- [関数の呼び出し規則](calling-conventions.md)

- [__Declspec](declspec.md)キーワードを使用して宣言された拡張ストレージクラス属性

- [__W64](w64.md)キーワード

## <a name="microsoft-specific-keywords"></a>Microsoft 固有キーワード

Microsoft 固有キーワードの多くは、宣言子を変更して派生型を作成する際に使用できます。 宣言子の詳細については、 [宣言子](./declarations-and-definitions-cpp.md)を参照してください。

|Keyword|説明|派生型を作成するために使用しますか?|
|-------------|-------------|---------------------------------|
|[__based](based-grammar.md)|これに続く名前は、宣言に含まれている 32 ビット ベースへの 32 ビット オフセットを宣言します。|はい|
|[__cdecl](cdecl.md)|これに続く名前は、C の命名規約と呼び出し規則を使用します。|はい|
|[__declspec](declspec.md)|これに続く名前は、Microsoft 固有のストレージ クラス属性を指定します。|いいえ|
|[__fastcall](fastcall.md)|これに続く名前は、引数を渡すためのスタックの代わりに、レジスタ (使用できる場合) を使用できる関数を宣言します。|はい|
|[__restrict](extension-restrict.md)|__Declspec ([制限](restrict.md)) に似ていますが、変数に使用します。|いいえ|
|[__stdcall](stdcall.md)|これに続く名前は、標準呼び出し規約を順守する関数を指定します。|はい|
|[__w64](w64.md)|64 ビット コンパイラでより大きいデータ型としてマークします。|いいえ|
|[__unaligned](unaligned.md)|型またはその他のデータへのポインターが配置されていないことを指定します。|いいえ|
|[__vectorcall](vectorcall.md)|これに続く名前は、引数を渡すためのスタックの代わりに、SSE レジスタを含むレジスタ (使用できる場合) を使用できる関数を宣言します。|はい|

## <a name="see-also"></a>関連項目

[C++ 言語リファレンス](cpp-language-reference.md)
