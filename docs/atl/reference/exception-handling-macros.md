---
title: 例外処理マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
dev_langs:
- C++
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05ee381aa792c252fc9b80107d25e15e7d1ecfca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358978"
---
# <a name="exception-handling-macros"></a>例外処理マクロ
これらのマクロは、例外処理のサポートを提供します。  
  
|||  
|-|-|  
|[_ATLCATCH](#_atlcatch)|関連する発生したエラーを処理するステートメント`_ATLTRY`です。|  
|[_ATLCATCHALL](#_atlcatchall)|関連する発生したエラーを処理するステートメント`_ATLTRY`です。|  
|[_ATLTRY](#_atltry)|エラーが発生する可能性があります、保護されたコード セクションをマークします。|  
  
## <a name="requirements"></a>要件:
**ヘッダー:** atldef.h

##  <a name="_atlcatch"></a>  _ATLCATCH  
 関連する発生したエラーを処理するステートメント`_ATLTRY`です。  
  
```
_ATLCATCH(e)
```  
  
### <a name="parameters"></a>パラメーター  
 *e*  
 キャッチする例外。  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用`_ATLTRY`です。 C++ に解決される[(CAtlException e) をキャッチ](../../cpp/try-throw-and-catch-statements-cpp.md)C++ 例外の指定された型を処理するためです。  
  
##  <a name="_atlcatchall"></a>  _ATLCATCHALL  
 関連する発生したエラーを処理するステートメント`_ATLTRY`です。  
  
```
_ATLCATCHALL
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用`_ATLTRY`です。 C++ に解決される[catch (...)](../../cpp/try-throw-and-catch-statements-cpp.md)すべての種類の C++ 例外を処理するためです。  
  
##  <a name="_atltry"></a>  _ATLTRY  
 エラーが発生する可能性があります、保護されたコード セクションをマークします。  
  
```
_ATLTRY
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用[_ATLCATCH](#_atlcatch)または[_ATLCATCHALL](#_atlcatchall)です。 C++ シンボルに解決される[再試行](../../cpp/try-throw-and-catch-statements-cpp.md)です。  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
