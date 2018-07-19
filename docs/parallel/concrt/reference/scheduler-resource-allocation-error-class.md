---
title: scheduler_resource_allocation_error クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3b11a548bc98c44697de45c628205dc3e720971
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686686"
---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error クラス
このクラスは、同時実行ランタイムでクリティカル リソースを取得できないためにスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class scheduler_resource_allocation_error : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[scheduler_resource_allocation_error](#ctor)|オーバーロードされます。 `scheduler_resource_allocation_error` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get_error_code](#get_error_code)|例外の原因となったエラー コードを返します。|  
  
## <a name="remarks"></a>コメント  
 同時実行ランタイムの内部から、オペレーティング システムへの呼び出しが失敗したときに、この例外はスロー通常。 通常は Win32 メソッドへの呼び出しから返されるエラー コード`GetLastError`型の値に変換されます`HRESULT`とを使用して取得できる、`get_error_code`メソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="get_error_code"></a> get_error_code 

 例外の原因となったエラー コードを返します。  
  
```
HRESULT get_error_code() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 `HRESULT`例外の原因となったエラーの値。  
  
##  <a name="ctor"></a> scheduler_resource_allocation_error 

 `scheduler_resource_allocation_error` オブジェクトを構築します。  
  
```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
 `_Hresult`  
 `HRESULT`例外の原因となったエラーの値。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
