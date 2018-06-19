---
title: LOGBRUSH 構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: 6e02c156619e4ca36d268870c70ba783c41a352d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375211"
---
# <a name="logbrush-structure"></a>LOGBRUSH 構造体
`LOGBRUSH`構造体は、スタイル、色、および物理的なブラシのパターンを定義します。 これは、Windows によって使用[CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487)と[構造体](http://msdn.microsoft.com/library/windows/desktop/dd162705)関数。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lbStyle`  
 ブラシのスタイルを指定します。 `lbStyle`メンバーは、次のスタイルのいずれかを指定する必要があります。  
  
- **BS_DIBPATTERN**ブラシをデバイスに依存しないビットマップ (DIB) 仕様で定義されるパターンです。 場合`lbStyle`は**BS_DIBPATTERN**、 **lbHatch**メンバーには、パックされた DIB へのハンドルが含まれています。  
  
- **BS_DIBPATTERNPT**ブラシをデバイスに依存しないビットマップ (DIB) 仕様で定義されるパターンです。 場合`lbStyle`は**BS_DIBPATTERNPT**、 **lbHatch**メンバーには、パックされた DIB へのポインターが含まれています。  
  
- **BS_HATCHED**ハッチ ブラシ。  
  
- **BS_HOLLOW**中空きブラシ。  
  
- **BS_NULL**と同じ**BS_HOLLOW**です。  
  
- **BS_PATTERN**メモリ ビットマップで定義されるパターン ブラシ。  
  
- **BS_SOLID**ソリッド ブラシ。  
  
 `lbColor`  
 描画するブラシの色を指定します。 場合`lbStyle`は、 **BS_HOLLOW**または**BS_PATTERN**スタイル、 **lbColor**は無視されます。 場合`lbStyle`は**BS_DIBPATTERN**または**BS_DIBPATTERNBT**の下位ワード**lbColor**を指定するかどうか、 **bmiColors**のメンバー、 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md)構造は、明示的な赤、緑、青 (RGB) の値またはインデックスを現在実現論理パレットに含まれています。 **LbColor**メンバーは、次の値のいずれかを指定する必要があります。  
  
- **DIB_PAL_COLORS**カラー テーブルは、現在実現論理パレットに 16 ビットのインデックスの配列で構成されています。  
  
- **DIB_RGB_COLORS**カラー テーブルには、リテラルの RGB 値が含まれています。  
  
 *lbHatch*  
 陰影のスタイルを指定します。 意味が異なりますで定義されているブラシ スタイル`lbStyle`です。 場合`lbStyle`は**BS_DIBPATTERN**、 **lbHatch**メンバーには、パックされた DIB へのハンドルが含まれています。 場合`lbStyle`は**BS_DIBPATTERNPT**、 **lbHatch**メンバーには、パックされた DIB へのポインターが含まれています。 場合`lbStyle`は**BS_HATCHED**、 **lbHatch**メンバーは、ハッチを作成するために使用する線の方向を指定します。 次の値のいずれかを指定できます。  
  
- `HS_BDIAGONAL` 45 度上、左から右へハッチ  
  
- `HS_CROSS` 水平および垂直方向の格子  
  
- `HS_DIAGCROSS` 45 度格子  
  
- `HS_FDIAGONAL` 45 度の下位方向へ、左から右へハッチ  
  
- `HS_HORIZONTAL` 水平方向の陰影  
  
- `HS_VERTICAL` 垂直方向の陰影  
  
 場合`lbStyle`は**BS_PATTERN**、 **lbHatch**パターンを定義するビットマップへのハンドルします。 場合`lbStyle`は**BS_SOLID**または**BS_HOLLOW**、 **lbHatch**は無視されます。  
  
## <a name="remarks"></a>コメント  
 **LbColor**ハッチ ブラシの前景の色を制御、 [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode)と[CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor)関数は、背景色を制御します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

