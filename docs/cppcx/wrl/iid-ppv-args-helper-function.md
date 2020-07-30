---
title: IID_PPV_ARGS_Helper 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: 6b1ab2e8e93fda194532fbc8d6f484aaa91249d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212970"
---
# <a name="iid_ppv_args_helper-function"></a>IID_PPV_ARGS_Helper 関数

指定された引数の型がインターフェイスから派生していることを確認し `IUnknown` ます。

> [!IMPORTANT]
> このテンプレートの特殊化は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。 代わりに[IID_PPV_ARGS](/windows/win32/api/combaseapi/nf-combaseapi-iid_ppv_args)を使用してください。

## <a name="syntax"></a>構文

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
引数*pp*の型。

*ページ*<br/>
二重間接ポインター。

## <a name="return-value"></a>戻り値

へのポインターへのポインターにキャストする引数*pp* **`void`** 。

## <a name="remarks"></a>解説

テンプレートパラメーター *T*がから派生していない場合、コンパイル時エラーが生成され `IUnknown` ます。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h
