---
title: BITMAPINFO 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- BITMAPINFO
dev_langs:
- C++
helpviewer_keywords:
- BITMAPINFO structure [MFC]
ms.assetid: a00caa49-e4df-419f-89a7-ab03c13a1b5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea99cfb77f295530f65b3d3b07888b0735fc0b6a
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950504"
---
# <a name="bitmapinfo-structure"></a>BITMAPINFO 構造体
`BITMAPINFO` 構造体は、Windows のデバイスに依存しないビットマップ (DIB: Device-Independent Bitmap) の寸法と色の情報を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagBITMAPINFO {  
    BITMAPINFOHEADER bmiHeader;  
    RGBQUAD bmiColors[1];  
} BITMAPINFO;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *bmiHeader*  
 指定します、 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)ディメンションとデバイスに依存しないビットマップの色の書式に関する情報を格納する構造体。  
  
 *bmiColors*  
 配列を指定[RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)または`DWORD`ビットマップの色を定義するデータ型。  
  
## <a name="remarks"></a>Remarks  
 デバイスに依存しないビットマップは、2 つの異なる部分から構成されます。ビットマップの寸法と色を表す `BITMAPINFO` 構造体と、ビットマップのピクセルを指定するバイトの配列です。 配列内のビットはパックされますが、各スキャン ラインには `LONG` 境界上で終わるように 0 が埋め込まれている必要があります。 高さが正の値のとき、ビットマップの原点は左下隅になります。 高さが負の値のとき、原点は左上隅になります。  
  
 A*パックされたビットマップ*ビットマップは、バイト配列が直後に、`BITMAPINFO`構造体。 パックされたビットマップは、1 つのポインターで参照されます。  
  
 詳細については、`BITMAPINFO`構造体し、のメンバーの適切な値、`BITMAPINFOHEADER`と`RGBQUAD`構造体は、Windows SDK ドキュメントの次のトピックを参照してください。  
  
- [BITMAPINFO 構造体](http://msdn.microsoft.com/library/windows/desktop/dd183375)  
  
- [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)構造体  
  
- [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)構造体  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)   
 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)

