---
title: TerminateMap 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 560f563e43fc8b818b04cd0bda6b01fbc916cb84
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213552"
---
# <a name="terminatemap-function"></a>TerminateMap 関数

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>パラメーター

*name*<br/>
[モジュール](module-class.md)。

*serverName*<br/>
パラメーター*モジュール*によって指定されたモジュール内のクラスファクトリのサブセットの名前。

*forceTerminate*<br/>
アクティブであるかどうかに関係なく、クラスファクトリを終了する**場合は true** 。ファクトリがアクティブな場合は、クラスファクトリを終了しない場合は**false** 。

## <a name="return-value"></a>戻り値

すべてのクラスファクトリが終了した場合は**true** 。それ以外の場合は**false**。

## <a name="remarks"></a>解説

指定されたモジュール内のクラスファクトリをシャットダウンします。

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>参照

[Microsoft::WRL::Details 名前空間](microsoft-wrl-details-namespace.md)
