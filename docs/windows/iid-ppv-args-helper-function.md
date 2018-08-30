---
title: IID_PPV_ARGS_Helper 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
dev_langs:
- C++
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a6131cea7a7684036fd7183a79214c7c6936540b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218749"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper 関数

指定された引数の型から派生することを確認、`IUnknown`インターフェイス。

> [!IMPORTANT]
> このテンプレートの特殊化は WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。 使用[IID_PPV_ARGS](https://msdn.microsoft.com/library/windows/desktop/ee330727.aspx)代わりにします。

## <a name="syntax"></a>構文

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>パラメーター

*T*  
引数の型*pp*します。

*pp*  
二重間接ポインター。

## <a name="return-value"></a>戻り値

引数*pp*ポインターにする-、- へのポインターにキャスト**void**します。

## <a name="remarks"></a>Remarks

コンパイル時エラーが生成テンプレート パラメーター *T*から派生していない`IUnknown`します。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

## <a name="see-also"></a>関連項目

[リファレンス (Windows ランタイム ライブラリ)](https://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)