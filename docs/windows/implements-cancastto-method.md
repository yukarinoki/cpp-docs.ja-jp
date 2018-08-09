---
title: Implements::cancastto メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a73aac6fb36270f0cd04615d9e530b29841850f8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010923"
---
# <a name="implementscancastto-method"></a>Implements::CanCastTo メソッド
指定したインターフェイスへのポインターを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *riid*  
 インターフェイス ID への参照  
  
 *ppv*  
 かどうかは成功すると、インターフェイスへのポインターで指定された*riid*します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、E_NOINTERFACE など、エラーを示す HRESULT。  
  
## <a name="remarks"></a>Remarks  
 これは、QueryInterface 操作を実行する内部のヘルパー関数です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Implements 構造体](../windows/implements-structure.md)