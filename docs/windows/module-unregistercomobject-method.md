---
title: Module::unregistercomobject メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 240ab47099b9e97e9a6bb794083858fe042605d2
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018696"
---
# <a name="moduleunregistercomobject-method"></a>Module::UnregisterCOMObject メソッド
他のアプリケーションが接続することが原因の 1 つまたは複数の COM オブジェクトを解除します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
virtual HRESULT UnregisterCOMObject(  
   const wchar_t* serverName,  
   DWORD* cookies,  
   unsigned int count  
```  
  
### <a name="parameters"></a>パラメーター  
 *サーバー名*  
 (未使用)  
  
 *Cookie*  
 登録するクラスのオブジェクトを識別する値へのポインターの配列。 配列がによって作成された、 [RegisterCOMObject](../windows/module-registercomobject-method.md)メソッド。  
  
 *count*  
 登録を解除するクラスの数。  
  
## <a name="return-value"></a>戻り値  
 この操作が成功した場合は s_ok を返します。それ以外の場合、エラーの理由を示す hresult 値の操作に失敗しました。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)