---
description: '詳細情報: Make 関数'
title: Make 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
ms.openlocfilehash: bb83c6c163440f911bc625a8646d1758442b25f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298904"
---
# <a name="make-function"></a>Make 関数

指定した Windows ランタイムクラスを初期化します。 同じモジュールで定義されているコンポーネントをインスタンス化するには、この関数を使用します。

## <a name="syntax"></a>構文

```cpp
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

### <a name="parameters"></a>パラメーター

*T*<br/>
から継承されるユーザー指定のクラス `WRL::RuntimeClass` 。

*TArg1*<br/>
指定されたランタイムクラスに渡される引数1の型。

*TArg2*<br/>
指定されたランタイムクラスに渡される引数2の型。

*TArg3*<br/>
指定されたランタイムクラスに渡される引数3の型。

*TArg4*<br/>
指定されたランタイムクラスに渡される引数4の型。

*TArg5*<br/>
指定されたランタイムクラスに渡される引数5の型。

*TArg6*<br/>
指定されたランタイムクラスに渡される引数6の型。

*TArg7*<br/>
指定されたランタイムクラスに渡される引数7の型。

*TArg8*<br/>
指定されたランタイムクラスに渡される引数8の型。

*TArg9*<br/>
指定されたランタイムクラスに渡される引数9の型。

*arg1*<br/>
指定されたランタイムクラスに渡される引数1。

*arg2*<br/>
指定されたランタイムクラスに渡される引数2。

*arg3*<br/>
指定されたランタイムクラスに渡される引数3。

*arg4*<br/>
指定されたランタイムクラスに渡される引数4。

*arg5*<br/>
指定されたランタイムクラスに渡される引数5。

*arg6*<br/>
指定されたランタイムクラスに渡される引数6。

*arg7*<br/>
指定されたランタイムクラスに渡される引数7。

*arg8*<br/>
引数8。指定されたランタイムクラスに渡されます。

*arg9*<br/>
指定されたランタイムクラスに渡される引数9。

## <a name="return-value"></a>戻り値

`ComPtr<T>`成功した場合はオブジェクト。それ以外の場合は **`nullptr`** 。

## <a name="remarks"></a>解説

「 [方法: Wrl コンポーネントを直接インスタンス化](how-to-instantiate-wrl-components-directly.md) する」を参照して、この関数と [Microsoft:: wrl::D Etails:: makeandinitialize](makeandinitialize-function.md)の違いを確認します。例については、「」を参照してください。

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
