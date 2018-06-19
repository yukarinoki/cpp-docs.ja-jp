---
title: DAO データベース エンジンの初期化と終了 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f28c0c166bcbf13181161d6afce484fe4a45b80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369903"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了
DAO データベース エンジンの有効期限がありますまず MFC DAO オブジェクトを使用するときに初期化され、終了、アプリケーションまたは DLL が終了する前にします。 2 つの関数、`AfxDaoInit`と`AfxDaoTerm`、これらのタスクを実行します。  
  
### <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|DAO データベース エンジンを初期化します。|  
|[AfxDaoTerm](#afxdaoterm)|データベース エンジンの初期化を終了します。|  
  
##  <a name="afxdaoinit"></a>  AfxDaoInit  
 この関数は、DAO データベース エンジンを初期化します。  
  
```  
 
void AfxDaoInit();

throw(CDaoException*);  
```  
  
### <a name="remarks"></a>コメント  
 ほとんどの場合に呼び出す必要はありません`AfxDaoInit`が必要なアプリケーションが自動的に呼び出すためです。  
  
 呼び出しの例については、関連情報については、`AfxDaoInit`を参照してください[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="afxdaoterm"></a>  AfxDaoTerm  
 この関数は、データベース エンジンの初期化を終了します。  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>コメント  
 通常、するだけで、通常の MFC DLL です。 この関数の呼び出しアプリケーションが自動的に呼び出す`AfxDaoTerm`が必要です。  
  
 標準の MFC Dll を呼び出す`AfxDaoTerm`する前に、`ExitInstance`関数の場合、すべての MFC DAO オブジェクトが破棄された後、そのします。  
  
 関連情報については、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)です。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
