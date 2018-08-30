---
title: LOGBRUSH 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure [MFC]
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b868efed07f786a78c516862e1f88d2310a7c05d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208779"
---
# <a name="logbrush-structure"></a>LOGBRUSH 構造体
`LOGBRUSH`構造体、スタイル、色、および物理的なブラシのパターンを定義します。 Windows で使用されて[CreateBrushIndirect](/windows/desktop/api/wingdi/nf-wingdi-createbrushindirect)と[構造体](/windows/desktop/api/wingdi/nf-wingdi-extcreatepen)関数。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *lbStyle*  
 ブラシのスタイルを指定します。 `lbStyle`メンバーは、次のスタイルのいずれかを指定する必要があります。  
  
- デバイスに依存しないビットマップ (DIB) 仕様で定義される BS_DIBPATTERN A パターンのブラシ。 場合*lbStyle* BS_DIBPATTERN には、`lbHatch`メンバーには、パックされた DIB を識別するハンドルが含まれています。  
  
- デバイスに依存しないビットマップ (DIB) 仕様で定義される BS_DIBPATTERNPT A パターンのブラシ。 場合*lbStyle* BS_DIBPATTERNPT には、`lbHatch`メンバーには、パックされた DIB へのポインターが含まれています。  
  
- BS_HATCHED ハッチ ブラシ。  
  
- BS_HOLLOW 白抜きのブラシ。  
  
- BS_NULL BS_HOLLOW と同じです。  
  
- BS_PATTERN パターンのメモリ ビットマップで定義されているブラシ。  
  
- BS_SOLID ソリッド ブラシ。  
  
 *lbColor*  
 描画するブラシの色を指定します。 場合*lbStyle* BS_HOLLOW または BS_PATTERN スタイルでは、 *lbColor*は無視されます。 場合*lbStyle* BS_DIBPATTERN または BS_DIBPATTERNBT の下位ワードは、 *lbColor*を指定するかどうか、`bmiColors`のメンバー、 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md)構造体現在実現論理パレットに明示的な赤、緑、青 (RGB) の値またはインデックスを含めることができます。 `lbColor`メンバーは、次の値のいずれかを指定する必要があります。  
  
- DIB_PAL_COLORS カラー テーブルは、現在の実現の論理パレットに 16 ビットのインデックスの配列で構成されます。  
  
- DIB_RGB_COLORS カラー テーブルには、リテラルの RGB 値が含まれています。  
  
 *lbHatch*  
 陰影のスタイルを指定します。 意味は、によって定義されているブラシ スタイルによって異なります。 *lbStyle*します。 場合*lbStyle* BS_DIBPATTERN には、`lbHatch`メンバーには、パックされた DIB を識別するハンドルが含まれています。 場合*lbStyle* BS_DIBPATTERNPT には、`lbHatch`メンバーには、パックされた DIB へのポインターが含まれています。 場合*lbStyle* BS_HATCHED には、`lbHatch`メンバーが、陰影を作成するために使用する線の方向を指定します。 次の値のいずれかを指定できます。  
  
- HS_BDIAGONAL A 45 度の上、左から右のハッチ  
  
- HS_CROSS 水平と垂直方向のハッチング  
  
- HS_DIAGCROSS 45 度のハッチング  
  
- HS_FDIAGONAL A 45 度の下、左から右のハッチ  
  
- 水平 HS_HORIZONTAL ハッチ  
  
- HS_VERTICAL 垂直ハッチ  
  
 場合*lbStyle*は BS_PATTERN、 *lbHatch*がパターンを定義するビットマップを識別するハンドル。 場合*lbStyle* BS_SOLID または BS_HOLLOW、 *lbHatch*は無視されます。  
  
## <a name="remarks"></a>Remarks  
 *LbColor*ハッチ ブラシの前景の色を制御、 [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode)と[CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor)関数は、背景色を制御します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

