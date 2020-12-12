---
description: '詳細情報: セグメント'
title: SEGMENT
ms.date: 12/16/2019
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: aeb99080043cbfb13fdec1c2e82df3a6d16b306d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97125594"
---
# <a name="segment"></a>SEGMENT

セグメント属性を持つ *name* というプログラムセグメントを定義します。

## <a name="syntax"></a>構文

> *名前***セグメント**⟦**READONLY**⟧⟦*align**⟧⟦⟧⟦*⟧*⟦⟧*⟦*⟧* **ALIAS (**_string_**)** __'__*class*__'__ \
> *命令*\
> *名前* の **終わり**

#### <a name="parameters"></a>パラメーター

*位置*\
セグメントの開始アドレスを選択できるメモリアドレスの範囲。 アラインメントの種類には、次のいずれかを指定できます。

|配置の種類|開始アドレス|
|----------------|----------------------|
|**BYTE**|次に使用可能なバイトアドレス。|
|**WORD**|次に使用可能な単語のアドレス (1 単語あたり2バイト)。|
|**DWORD**|次に使用可能な2つの単語のアドレス (2 単語あたり4バイト)。|
|**割り付け**|次に使用できる段落アドレス (1 段落あたり16バイト)。|
|**改**|次に使用可能なページアドレス (ページあたり256バイト)。|
|**ALIGN**(*n*)|次に使用可能な *n* 番目のバイトアドレス。 詳細については、「解説」を参照してください。|

このパラメーターが指定されていない場合、既定では [ **段落** ] が使用されます。

*結合* (32 ビット MASM のみ) \
**パブリック**、**スタック**、**共通**、**メモリ**、 <em>アドレス</em>、**プライベート**

*使用* (32 ビット MASM のみ) \
**USE16**、 **USE32**、 **FLAT**

*外観*\
**INFO**、 **READ**、 **WRITE**、 **EXECUTE**、 **SHARED**、 **nopage**、 **NOCACHE**、および **DISCARD**

これらは COFF に対してのみサポートされ、COFF セクションの類似する名前の特性に対応します (たとえば、 **SHARED** は IMAGE_SCN_MEM_SHARED に対応します)。 READ IMAGE_SCN_MEM_READ フラグを設定します。 不使用の READONLY フラグが原因で、セクションの IMG_SCN_MEM_WRITE フラグがクリアされました。 いずれかの *特性* が設定されている場合、既定の特性は使用されず、プログラマが指定したフラグのみが有効になります。

_文字列_\
この文字列は、出力された COFF オブジェクトのセクション名として使用されます。  同じ外部名を持つ複数のセクションを作成し、それぞれに異なる MASM セグメント名を付けます。

**/Omf** ではサポートされていません。

*講義*\
アセンブルされたファイル内でセグメントを結合および順序付けする方法を指定します。 一般的な値は、、、 `'DATA'` `'CODE'` 、 `'CONST'` およびです。 `'STACK'`

## <a name="remarks"></a>解説

の場合 `ALIGN(n)` 、 *n* は 1 ~ 8192 の任意の累乗になります。 **/omf** ではサポートされていません。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)
