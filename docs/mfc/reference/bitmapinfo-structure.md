---
title: BITMAPINFO 構造体 |Microsoft Docs
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
ms.openlocfilehash: 0bc5adbb62e70a012d9dff4f9a390a46476aaa36
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200257"
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
 指定します、 [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376)ディメンションとデバイスに依存しないビットマップの色の書式に関する情報を含む構造体。  
  
 *bmiColors*  
 配列を指定します[RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad)またはビットマップの色を定義する DWORD データ型。  
  
## <a name="remarks"></a>Remarks  
 デバイスに依存しないビットマップは、2 つの異なる部分から構成されます。ビットマップの寸法と色を表す `BITMAPINFO` 構造体と、ビットマップのピクセルを指定するバイトの配列です。 配列内のビットはパックしますが、各スキャン ラインに終了のゼロを埋め込む必要があります、**長い**境界。 高さが正の値のとき、ビットマップの原点は左下隅になります。 高さが負の値のとき、原点は左上隅になります。  
  
 A*パックされたビットマップ*ビットマップは、バイト配列が直後に、`BITMAPINFO`構造体。 パックされたビットマップは、1 つのポインターで参照されます。  
  
 詳細については、`BITMAPINFO`構造体のメンバーの適切な値であり、`BITMAPINFOHEADER`と`RGBQUAD`構造体は、Windows SDK のドキュメントでは、次のトピックを参照してください。  
  
- [BITMAPINFO 構造体](/windows/desktop/api/wingdi/ns-wingdi-tagbitmapinfo)  
  
- [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376)構造体  
  
- [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad)構造体  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBrush::CreateDIBPatternBrush](../../mfc/reference/cbrush-class.md#createdibpatternbrush)   
 [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376)   
 [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad)

