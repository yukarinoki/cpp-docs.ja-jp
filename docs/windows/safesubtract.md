---
title: SafeSubtract |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeSubtract
dev_langs:
- C++
helpviewer_keywords:
- SafeSubtract function
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a82281f1078acd5e3ed0662964a0171ccd72c336
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018375"
---
# <a name="safesubtract"></a>SafeSubtract
オーバーフローに対する保護できる方法で 2 つの数値を減算します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*t*  
 減算の最初の数値。 これは、型でなければなりません`T`します。  
  
 [in]*u*  
 減算する数値*t*します。 これは、型でなければなりません`U`します。  
  
 [out]*結果*  
 パラメーターで**SafeSubtract**結果を格納します。  
  
## <a name="return-value"></a>戻り値  
 **true**場合、エラーは発生しません。**false**エラーが発生した場合。  
  
## <a name="remarks"></a>Remarks  
 このメソッドの一部は、 [SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成せず 1 つの減算演算のものでは、 [SafeInt クラス](../windows/safeint-class.md)します。  
  
> [!NOTE]
>  このメソッドは、単一の数値演算を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数の呼び出しではなくクラス。  
  
 テンプレートの種類の詳細については`T`と`U`を参照してください[SafeInt 関数](../windows/safeint-functions.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt 関数](../windows/safeint-functions.md)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)   
 [SafeAdd](../windows/safeadd.md)