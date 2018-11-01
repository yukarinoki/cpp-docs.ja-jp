---
title: SEGMENT
ms.date: 08/30/2018
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: f37be47b92a71e20821cd1e40f8cf1350dfedaff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615424"
---
# <a name="segment"></a>SEGMENT

定義と呼ばれるプログラム セグメント*名前*セグメント属性を持つ

## <a name="syntax"></a>構文

> *名前*セグメント [READONLY] [*align*] [*結合*] [*使用*] [*特性*] エイリアス (*文字列*) ['*クラス*']<br/>
> *ステートメント*<br/>
> *名前*終了

#### <a name="parameters"></a>パラメーター

*align*<br/>
セグメントの開始アドレスを選択できるメモリ アドレスの範囲。 配置の種類は、次のいずれかにできます。

|配置の種類|開始アドレス|
|----------------|----------------------|
|**BYTE**|[次へ] の使用可能なバイトのアドレス。|
|**WORD**|次に利用可能な word アドレス (2 バイト ワードあたり)。|
|**DWORD**|次にダブル ワードを使用可能なアドレス (ダブル ワードあたり 4 バイト)。|
|**PARA**|次の段落が使用可能なアドレス (1 つの段落は 16 バイト)。|
|**PAGE**|次に利用できるページ アドレス (1 ページあたりの 256 バイト)。|
|**ALIGN**(*n*)|[次へ] 使用可能な*n*番目のバイトのアドレス。 詳細については「解説」を参照してください。|

このパラメーターが指定されていない場合**PARA**既定で使用されます。

*combine*<br/>
**パブリック**、**スタック**、**共通**、**メモリ**、**で**<em>アドレス</em>、 **プライベート**

*use*<br/>
**USE16**、 **USE32**、**フラット**

*特性*<br/>
**情報**、**読み取り**、**書き込み**、 **EXECUTE**、 **SHARED**、 **NOPAGE**、 **NOCACHE**、および**破棄**

これら COFF ののみがサポートし、類似した名前の COFF セクション特性に対応しています (たとえば、 **SHARED** IMAGE_SCN_MEM_SHARED に対応しています)。 読み取りは、IMAGE_SCN_MEM_READ フラグを設定します。 古い形式の読み取り専用フラグの原因となった IMG_SCN_MEM_WRITE フラグをクリアするセクション。 存在する場合*特性*既定の特性は使用されず、プログラマが指定したフラグのみが有効に設定されます。

`ALIAS(` *文字列* `)`<br/>
この文字列は、生成された COFF オブジェクト内のセクション名として使用されます。  異なる MASM セグメント名では、同じ外部名を複数のセクションを作成します。

サポートされていません **/omf**します。

*class*<br/>
セグメントを結合して、アセンブルされたファイルで順序付けする方法を指定します。 通常、この値は、 `'DATA'`、 `'CODE'`、`'CONST'`と `'STACK'`

## <a name="remarks"></a>Remarks

`ALIGN(n)`、 *N*は 1 から 8192 の 2 の累乗があります。 でサポートされていません **/omf**します。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>