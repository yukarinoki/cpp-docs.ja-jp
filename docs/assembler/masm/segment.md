---
title: SEGMENT
ms.date: 08/30/2018
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: b7344d9cb685e0212748d7835e19f398f14979e7
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74393724"
---
# <a name="segment"></a>SEGMENT

セグメント属性を持つ*name*というプログラムセグメントを定義します。

## <a name="syntax"></a>構文

> *名前***セグメント**⟦**READONLY**⟧⟦*align* *⟧⟦⟧⟦* ⟧ *⟦⟧* ⟦ *⟧* **ALIAS (** _string_ **)** __'__ *class* __'__ \
> *ステートメント*の\
> *名前*の**終わり**

#### <a name="parameters"></a>パラメーター

*align*<br/>
セグメントの開始アドレスを選択できるメモリアドレスの範囲。 アラインメントの種類には、次のいずれかを指定できます。

|配置の種類|開始アドレス|
|----------------|----------------------|
|**BYTE**|次に使用可能なバイトアドレス。|
|**WORD**|次に使用可能な単語のアドレス (1 単語あたり2バイト)。|
|**DWORD**|次に使用可能な2つの単語のアドレス (2 単語あたり4バイト)。|
|**割り付け**|次に使用できる段落アドレス (1 段落あたり16バイト)。|
|**PAGE**|次に使用可能なページアドレス (ページあたり256バイト)。|
|**ALIGN**(*n*)|次に使用可能な*n*番目のバイトアドレス。 詳細については、「解説」を参照してください。|

このパラメーターが指定されていない場合、既定では **[段落]** が使用されます。

*結合*\
**パブリック**、**スタック**、**共通**、**メモリ**、<em>アドレス</em>、**プライベート**

\*を使用する*
**USE16**、 **USE32**、 **FLAT**

*特性*\
**INFO**、 **READ**、 **WRITE**、 **EXECUTE**、 **SHARED**、 **nopage**、 **NOCACHE**、および**DISCARD**

これらは COFF に対してのみサポートされ、COFF セクションの類似する名前の特性に対応します (たとえば、 **SHARED**は IMAGE_SCN_MEM_SHARED に対応します)。 READ IMAGE_SCN_MEM_READ フラグを設定します。 不使用の READONLY フラグが原因で、セクションの IMG_SCN_MEM_WRITE フラグがクリアされました。 いずれかの*特性*が設定されている場合、既定の特性は使用されず、プログラマが指定したフラグのみが有効になります。

_string_\
この文字列は、出力された COFF オブジェクトのセクション名として使用されます。  同じ外部名を持つ複数のセクションを作成し、それぞれに異なる MASM セグメント名を付けます。

**/Omf**ではサポートされていません。

*class*\
アセンブルされたファイル内でセグメントを結合および順序付けする方法を指定します。 一般的な値は、、`'DATA'`、`'CODE'`、`'CONST'`、および `'STACK'`

## <a name="remarks"></a>コメント

`ALIGN(n)`の場合、 *n*は 1 ~ 8192 の2の累乗になります。 **/omf**ではサポートされていません。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)
