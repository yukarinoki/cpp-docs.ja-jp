---
title: CInvalidArgException クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
dev_langs:
- C++
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a71802a4544ae238474a0747d879d29c69f6ba19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366750"
---
# <a name="cinvalidargexception-class"></a>CInvalidArgException クラス
このクラスは、無効な引数の例外状態を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CInvalidArgException : public CSimpleException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|コンストラクターです。|  
  
## <a name="remarks"></a>コメント  
 A`CInvalidArgException`オブジェクトが無効な引数の例外条件を表します。  
  
 例外処理の詳細については、次を参照してください。、 [CException クラス](../../mfc/reference/cexception-class.md)トピックおよび[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CInvalidArgException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cinvalidargexception"></a>  CInvalidArgException::CInvalidArgException  
 コンストラクターです。  
  
```  
CInvalidArgException();
```  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接使用しないでください。グローバル関数を呼び出す**AfxThrowInvalidArgException**です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSimpleException クラス](../../mfc/reference/csimpleexception-class.md)
