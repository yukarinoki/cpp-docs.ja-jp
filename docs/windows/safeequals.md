---
title: SafeEquals |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeEquals function
ms.assetid: 6019627d-f170-413b-9abd-2b5b34396a72
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 510d5490cdd400465c2743f194dc698daf9e1e55
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018160"
---
# <a name="safeequals"></a>SafeEquals
等しいかどうかを判断する 2 つの数値を比較します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<typename T, typename U>  
inline bool SafeEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*t*  
 比較する最初の数値。 これは T 型である必要があります。  
  
 [in]*u*  
 比較する 2 番目の数値。 これは、型 U のある必要があります。  
  
## <a name="return-value"></a>戻り値  
 **true**場合*t*と*u*はそれ以外の**false**します。  
  
## <a name="remarks"></a>Remarks  
 メソッドを強化`==`ため**SafeEquals** 2 つの異なる型の数値を比較することができます。  
  
 このメソッドの一部は、 [SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成せず、単一の比較操作のものでは、 [SafeInt クラス](../windows/safeint-class.md)します。  
  
> [!NOTE]
>  このメソッドは、単一の数値演算を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数の呼び出しではなくクラス。  
  
 T および U のテンプレートの種類の詳細については、次を参照してください。 [SafeInt 関数](../windows/safeint-functions.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt 関数](../windows/safeint-functions.md)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeNotEquals](../windows/safenotequals.md)