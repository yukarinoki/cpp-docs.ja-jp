---
title: Safeintexception::safeintexception |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ef3c1d11c0f814699ca1492f7ec1fb49c43c3d76
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException

          `SafeIntException` オブジェクトを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `code`  
 発生したエラーを説明する列挙値。  
  
## <a name="remarks"></a>コメント  
 値は、使用可能な`code`Safeint.h ファイルで定義されます。 便宜上、使用可能な値は、次に示します。  
  
-   `SafeIntNoError`  
  
-   `SafeIntArithmeticOverflow`  
  
-   `SafeIntDivideByZero`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>関連項目  
 [SafeInt ライブラリ](../windows/safeint-library.md)   
 [SafeIntException クラス](../windows/safeintexception-class.md)   
 [SafeInt クラス](../windows/safeint-class.md)