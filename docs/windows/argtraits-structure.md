---
title: ArgTraits 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
dev_langs:
- C++
helpviewer_keywords:
- ArgTraits structure
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df5f341382b7f9594d740b7e47fbb53b53188d75
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643122"
---
# <a name="argtraits-structure"></a>ArgTraits 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<typename TMemberFunction>  
struct ArgTraits;  
template<typename TDelegateInterface>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;  
```  
  
### <a name="parameters"></a>パラメーター  
 *TMemberFunction*  
 Typename パラメーターことはできませんと一致する ArgTraits 構造体の`Invoke`メソッド シグネチャ。  
  
 *TDelegateInterface*  
 デリゲートのインターフェイスです。  
  
 *TArg1*  
 最初の引数の型、`Invoke`メソッド。  
  
 *TArg2*  
 2 番目の引数の型、`Invoke`メソッド。  
  
 *TArg3*  
 3 番目の引数の型、`Invoke`メソッド。  
  
 *TArg4*  
 4 番目の引数の型、`Invoke`メソッド。  
  
 *TArg5*  
 5 番目の引数の型、`Invoke`メソッド。  
  
 *TArg6*  
 6 番目の引数の型、`Invoke`メソッド。  
  
 *TArg7*  
 7 番目の引数の型、`Invoke`メソッド。  
  
 *TArg8*  
 8 番目の引数の型、`Invoke`メソッド。  
  
 *TArg9*  
 9 番目の引数の型、`Invoke`メソッド。  
  
## <a name="remarks"></a>Remarks  
 **ArgTraits**構造体は、インターフェイス、およびパラメーターの数が指定された匿名のメンバー関数に指定したデリゲートを宣言します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Arg1Type`|TArg1 の typedef。|  
|`Arg2Type`|TArg2 の typedef。|  
|`Arg3Type`|TArg3 の typedef。|  
|`Arg4Type`|TArg4 の typedef。|  
|`Arg5Type`|TArg5 の typedef。|  
|`Arg6Type`|TArg6 の typedef。|  
|`Arg7Type`|TArg7 の typedef。|  
|`Arg8Type`|TArg8 の typedef。|  
|`Arg9Type`|TArg9 の typedef。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|name|説明|  
|----------|-----------------|  
|[ArgTraits::args 定数](../windows/argtraits-args-constant.md)|パラメーターの数のカウントを保持、`Invoke`デリゲート インターフェイスのメソッド。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ArgTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)