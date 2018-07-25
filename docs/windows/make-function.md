---
title: Make 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
dev_langs:
- C++
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f381a00b5ac1f105080355f1d3e3cd15efa5abf8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878074"
---
# <a name="make-function"></a>Make 関数
指定した Windows ランタイム クラスを初期化します。 同じモジュールで定義されているコンポーネントのインスタンスを作成するのにには、この関数を使用します。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename T,  
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
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8,  
   TArg9 &&arg9  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2  
);  
template <  
   typename T,  
   typename TArg1  
>  
ComPtr<T> Make(  
   TArg1 &&arg1  
);  
template <  
   typename T  
>  
ComPtr<T> Make();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ユーザー指定のクラスから継承する`WRL::RuntimeClass`です。  
  
 `TArg1`  
 1 の指定したランタイム クラスに渡される引数の型。  
  
 `TArg2`  
 指定したランタイム クラスに渡される引数 2 の型。  
  
 `TArg3`  
 指定したランタイム クラスに渡される 3 の引数の型。  
  
 `TArg4`  
 指定したランタイム クラスに渡される引数 4 の型。  
  
 `TArg5`  
 指定したランタイム クラスに渡される 5 の引数の型。  
  
 `TArg6`  
 指定したランタイム クラスに渡される 6 の引数の型。  
  
 `TArg7`  
 指定したランタイム クラスに渡される 7 の引数の型。  
  
 `TArg8`  
 指定したランタイム クラスに渡される 8 の引数の型。  
  
 `TArg9`  
 指定したランタイム クラスに渡される 9 の引数の型。  
  
 `arg1`  
 指定したランタイム クラスに渡される引数 1 です。  
  
 `arg2`  
 指定したランタイム クラスに渡される引数 2 です。  
  
 `arg3`  
 指定したランタイム クラスに渡される引数 3 です。  
  
 `arg4`  
 指定したランタイム クラスに渡される引数 4 です。  
  
 `arg5`  
 指定したランタイム クラスに渡される引数 5 です。  
  
 `arg6`  
 指定したランタイム クラスに渡される引数 6 です。  
  
 `arg7`  
 指定したランタイム クラスに渡される引数 7 です。  
  
 `arg8`  
 指定したランタイム クラスに渡される引数 8 です。  
  
 `arg9`  
 指定したランタイム クラスに渡される引数 9 です。  
  
## <a name="return-value"></a>戻り値  
 A`ComPtr<T>`成功、それ以外の場合は、オブジェクト`nullptr`です。  
  
## <a name="remarks"></a>コメント  
 参照してください[する方法: 直接に WRL コンポーネントをインスタンス化](../windows/how-to-instantiate-wrl-components-directly.md)この関数の間の違いについて学習して[Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)、および例についてはします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)