---
title: '既定値:: (type_name)::equals メソッド |Microsoft ドキュメント'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::Object::Equals
dev_langs:
- C++
ms.assetid: 4450f835-06fc-4758-8d0a-72cf00007873
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d2a8246597715ee2be2f55ba396a57f0ed014819
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="defaulttypenameequals-method"></a>default::(type_name)::Equals メソッド
指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
  
bool Equals(  
    Object^ obj  
)  
```  
  
### <a name="parameters"></a>パラメーター  
 obj  
 比較対象のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが等しい場合は`true` 。それ以外の場合は `false`。  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** 既定  
  
 **ヘッダー:** vccorlib.h  
  
## <a name="see-also"></a>関連項目  
 [default 名前空間](../cppcx/default-namespace.md)