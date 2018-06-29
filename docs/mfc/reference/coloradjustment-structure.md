---
title: COLORADJUSTMENT 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COLORADJUSTMENT
dev_langs:
- C++
helpviewer_keywords:
- COLORADJUSTMENT structure [MFC]
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1bb4cba5ef2eafa27a26c945f8754eb1a0ab0315
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37077956"
---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT 構造体
`COLORADJUSTMENT`構造体は、Windows によって使用される色の調整値を定義`StretchBlt`と`StretchDIBits`関数と、`StretchBlt`モードは**ハーフトーン**です。  
  
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
 *caSize*  
 構造体のサイズを指定します (バイト単位)。  
  
 *caFlags*  
 出力イメージを準備する方法を指定します。 このメンバーを設定することができます**NULL**または、次の値の任意の組み合わせ。  
  
- **CA_NEGATIVE**元のイメージの負の値を表示することを指定します。  
  
- **CA_LOG_FILTER**最終的な出力の色の濃さを対数関数が適用されることを指定します。 輝度が少ないときに、色コントラストが増加します。  
  
 *caIlluminantIndex*  
 イメージのオブジェクトが表示されるの光源の輝度を指定します。 このメンバーは、次の値のいずれかに設定できます。  
  
- **ILLUMINANT_EQUAL_ENERGY**  
  
- **ILLUMINANT_A**  
  
- **ILLUMINANT_B**  
  
- **ILLUMINANT_C**  
  
- **ILLUMINANT_D50**  
  
- **ILLUMINANT_D55**  
  
- **ILLUMINANT_D65**  
  
- **ILLUMINANT_D75**  
  
- **ILLUMINANT_F2**  
  
- **ILLUMINANT_TURNGSTEN**  
  
- **ILLUMINANT_DAYLIGHT**  
  
- **ILLUMINANT_FLUORESCENT**  
  
- **ILLUMINANT_NTSC**  
  
 *caRedGamma*  
 ソースの色の赤のプライマリ n 番目の電力のガンマ補正値を指定します。 値は、2,500 から 65,000 の範囲である必要があります。 10,000 の値は、ガンマ補正がないことを意味します。  
  
 *caGreenGamma*  
 ソースの色の緑のプライマリ n 番目の電力のガンマ補正値を指定します。 値は、2,500 から 65,000 の範囲である必要があります。 10,000 の値は、ガンマ補正がないことを意味します。  
  
 *caBlueGamma*  
 ソースの色の青のプライマリ n 番目の電力のガンマ補正値を指定します。 値は、2,500 から 65,000 の範囲である必要があります。 10,000 の値は、ガンマ補正がないことを意味します。  
  
 *caReferenceBlack*  
 ソース カラーに対して黒の参照を指定します。 これよりも暗い色は黒として扱われます。 値は、0 ~ 4,000 の範囲にする必要があります。  
  
 *caReferenceWhite*  
 ソース カラーの白の参照を指定します。 これより明るい色は白として扱われます。 値は、6,000 から 10,000 までの範囲にする必要があります。  
  
 *caContrast*  
 ソース オブジェクトに適用されるコントラストの量を指定します。 値は、100 ~-100 の範囲にする必要があります。 値 0 はコントラストの調整がないことを意味します。  
  
 *caBrightness*  
 ソース オブジェクトに適用される明るさの量を指定します。 値は、100 ~-100 の範囲にする必要があります。 値 0 は、明るさの調整がないことを意味します。  
  
 *caColorfulness*  
 ソース オブジェクトに適用される彩度の量を指定します。 値は、100 ~-100 の範囲にする必要があります。 値 0 は、彩度の調整がないことを意味します。  
  
 *caRedGreenTint*  
 ソース オブジェクトに適用する赤または緑の濃淡調整の量を指定します。 値は、100 ~-100 の範囲にする必要があります。 正の数値は赤色方向、負の数値が緑に調整します。 0 は、濃淡調整がないことを意味します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)


