---
title: COLORADJUSTMENT 構造体
ms.date: 11/04/2016
f1_keywords:
- COLORADJUSTMENT
helpviewer_keywords:
- COLORADJUSTMENT structure [MFC]
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
ms.openlocfilehash: 4f25b8241c1862a9c12d405ee5d47d5553dd6e29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623510"
---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT 構造体

`COLORADJUSTMENT`構造体は、Windows によって使用される色の調整値を定義します。`StretchBlt`と`StretchDIBits`関数と、`StretchBlt`モードはハーフトーンします。

## <a name="syntax"></a>構文

```
typedef struct  tagCOLORADJUSTMENT {    /* ca */
    WORD caSize;
    WORD caFlags;
    WORD caIlluminantIndex;
    WORD caRedGamma;
    WORD caGreenGamma;
    WORD caBlueGamma;
    WORD caReferenceBlack;
    WORD caReferenceWhite;
    SHORT caContrast;
    SHORT caBrightness;
    SHORT caColorfulness;
    SHORT caRedGreenTint;
} COLORADJUSTMENT;
```

#### <a name="parameters"></a>パラメーター

*caSize*<br/>
構造体のサイズをバイトで指定します。

*caFlags*<br/>
出力のイメージを準備する方法を指定します。 このメンバーは、NULL または次の値の任意の組み合わせを設定できます。

- CA_NEGATIVE では、元のイメージの負の値を表示することを指定します。

- CA_LOG_FILTER では、最終的な出力色の濃さを対数関数が適用されることを指定します。 輝度が少ないときに、色のコントラストが増加します。

*caIlluminantIndex*<br/>
イメージ オブジェクトが表示される光の光源の輝度を指定します。 このメンバーは、次の値のいずれかに設定できます。

- ILLUMINANT_EQUAL_ENERGY

- ILLUMINANT_A

- ILLUMINANT_B

- ILLUMINANT_C

- ILLUMINANT_D50

- ILLUMINANT_D55

- ILLUMINANT_D65

- ILLUMINANT_D75

- ILLUMINANT_F2

- ILLUMINANT_TURNGSTEN

- ILLUMINANT_DAYLIGHT

- ILLUMINANT_FLUORESCENT

- ILLUMINANT_NTSC

*caRedGamma*<br/>
元の色の原色の赤の n 番目の電源のガンマ補正値を指定します。 値は、2,500 から 65,000 の範囲内で指定する必要があります。 10,000 の値は、ガンマ補正がないことを意味します。

*caGreenGamma*<br/>
元の色の原色の緑色の n 番目の電源のガンマ補正値を指定します。 値は、2,500 から 65,000 の範囲内で指定する必要があります。 10,000 の値は、ガンマ補正がないことを意味します。

*caBlueGamma*<br/>
元の色の原色の青の n 番目の電源のガンマ補正値を指定します。 値は、2,500 から 65,000 の範囲内で指定する必要があります。 10,000 の値は、ガンマ補正がないことを意味します。

*caReferenceBlack*<br/>
元の色を黒の参照を指定します。 これより暗い色は黒として扱われます。 値は、0 ~ 4,000 の範囲である必要があります。

*caReferenceWhite*<br/>
元の色を白の参照を指定します。 これよりも明るい色は白として扱われます。 値は、6,000 から 10,000 までの範囲でなければなりません。

*caContrast*<br/>
ソース オブジェクトに適用するコントラストの量を指定します。 値は 100 ~-100 の範囲でなければなりません。 値 0 は、コントラストの調整がないことを意味します。

*caBrightness*<br/>
ソース オブジェクトに適用される明るさの量を指定します。 値は 100 ~-100 の範囲でなければなりません。 値 0 は、明るさの調整がないことを意味します。

*caColorfulness*<br/>
ソース オブジェクトに適用する彩度の量を指定します。 値は 100 ~-100 の範囲でなければなりません。 値 0 は、彩度の調整がないことを意味します。

*caRedGreenTint*<br/>
ソース オブジェクトに適用する赤または緑の濃淡の調整の量を指定します。 値は 100 ~-100 の範囲でなければなりません。 正の数値が赤に調整して、負の数値が緑に調整します。 0 は濃淡の調整を意味します。

## <a name="requirements"></a>必要条件

**ヘッダー:** wingdi.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)

