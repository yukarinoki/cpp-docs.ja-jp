---
title: alloc_text
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
ms.openlocfilehash: 399e8956a511f289b480e66db7f03cac0a6c7c20
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031366"
---
# <a name="alloctext"></a>alloc_text
指定した関数定義が存在するコード セクションに名前を付けます。 このプラグマは、名前付き関数の関数宣言子と関数定義との間で指定する必要があります。

## <a name="syntax"></a>構文

```
#pragma alloc_text( "
textsection
", function1, ... )
```

## <a name="remarks"></a>Remarks

**Alloc_text**プラグマが処理しないC++メンバー関数またはオーバー ロードされた関数。 C リンケージで宣言された関数のみに適用することで宣言された関数、 **extern"C"** リンケージ指定します。 C++ リンケージを持つ関数でこのプラグマを使用しようとすると、コンパイラ エラーが生成されます。

関数のアドレス指定を使用して以降`__based`はサポートされていません、セクションの場所を使用する必要を指定する、 **alloc_text**プラグマ。 指定された名前*textsection*二重引用符で囲む必要があります。

**Alloc_text**プラグマとこれらの関数の定義の前に指定された関数のいずれかの宣言の後に表示する必要があります。

参照される関数、 **alloc_text**プラグマは、プラグマと同じモジュールで定義する必要があります。 これが実行されず、未定義の関数が別のテキスト セクションに後でコンパイルされると、エラーがキャッチされる場合とキャッチされない場合があります。 プログラムは正常に動作しますが、関数は目的のセクションでは割り当てられません。

その他の制限**alloc_text**次に示します。

- 関数内では使用できません。

- 関数が宣言された後で、関数が定義される前に使用する必要があります。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)