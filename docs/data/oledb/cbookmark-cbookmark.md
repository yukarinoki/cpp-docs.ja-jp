---
title: Cbookmark::cbookmark |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
dev_langs:
- C++
helpviewer_keywords:
- CBookmark class, constructor
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f7663c34fc9eea5f4262fea6b347c1b7899ace85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cbookmarkcbookmark"></a>CBookmark::CBookmark
コンストラクターです。  
  
## <a name="syntax"></a>構文  
  
```cpp
      CBookmark();   

CBookmark(DBLENGTH nSize);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nSize`  
 [in]ブックマークのバッファーのサイズ (バイト単位)。  
  
## <a name="remarks"></a>コメント  
 最初の関数では、バッファーを設定**NULL**バッファー サイズが 0 です。 2 番目の関数では、バッファー サイズを設定`nSize`、およびバッファーのバイト配列を`nSize`バイトです。  
  
> [!NOTE]
>  この関数はでのみ使用**CBookmark\<0 >** です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CBookmark クラス](../../data/oledb/cbookmark-class.md)