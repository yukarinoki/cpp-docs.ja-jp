---
description: '詳細情報: TerminateMap 関数'
title: TerminateMap 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 919759d0b4b7f67cf3aff83c3e83678860d0badc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135064"
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

*第*<br/>
[モジュール](module-class.md)。

*serverName*<br/>
パラメーター *モジュール* によって指定されたモジュール内のクラスファクトリのサブセットの名前。

*forceTerminate*<br/>
**`true`** アクティブになっているかどうかに関係なく、クラスファクトリを終了するには **`false`** 任意のファクトリがアクティブな場合に、クラスファクトリを終了しないようにする場合は。

## <a name="return-value"></a>戻り値

**`true`** すべてのクラスファクトリが終了した場合は。それ以外の場合は **`false`** 。

## <a name="remarks"></a>解説

指定されたモジュール内のクラスファクトリをシャットダウンします。

## <a name="requirements"></a>要件

**ヘッダー:** resource.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>関連項目

[Microsoft:: WRL::D etails 名前空間](microsoft-wrl-details-namespace.md)
