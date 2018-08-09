---
title: SafeCast |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeCast
dev_langs:
- C++
helpviewer_keywords:
- SafeCast function
ms.assetid: 55316729-8456-403a-9f96-59d4038f67af
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 07311e916fa78f1ba946ad4631905968912f8195
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019067"
---
# <a name="safecast"></a>SafeCast
型の数値を別の型にキャストします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<typename T, typename U>  
inline bool SafeCast (  
   const T From,  
   U& To  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*から*  
 変換するソースの数。 これは、型でなければなりません`T`します。  
  
 [out]*に*  
 新しい数値型への参照。 これは、型でなければなりません`U`します。  
  
## <a name="return-value"></a>戻り値  
 **true**場合、エラーは発生しません。**false**エラーが発生した場合。  
  
## <a name="remarks"></a>Remarks  
 このメソッドの一部は、 [SafeInt ライブラリ](../windows/safeint-library.md)のインスタンスを作成せず、1 つのキャスト操作のものでは、 [SafeInt クラス](../windows/safeint-class.md)します。  
  
> [!NOTE]
>  このメソッドは、1 つの操作を保護する必要がありますにのみ使用する必要があります。 使用する必要があります複数の操作がある場合、`SafeInt`個々 のスタンドアロン関数の呼び出しではなくクラス。  
  
 T および U のテンプレートの種類の詳細については、次を参照してください。 [SafeInt 関数](../windows/safeint-functions.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt 関数](../windows/safeint-functions.md)   
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeInt クラス](../windows/safeint-class.md)