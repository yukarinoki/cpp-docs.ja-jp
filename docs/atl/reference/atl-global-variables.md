---
description: 詳細については、「ATL グローバル変数」を参照してください。
title: ATL グローバル変数
ms.date: 12/06/2017
f1_keywords:
- ATLBASE/_pAtlModule
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
ms.openlocfilehash: 8d0544651e32f5e569973466af8ce04af1433766
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158778"
---
# <a name="atl-global-variables"></a>ATL グローバル変数

## <a name="_patlmodule"></a>_pAtlModule

現在のモジュールへのポインターを格納するグローバル変数。

```cpp
__declspec(selectany) CAtlModule * _pAtlModule
```

### <a name="remarks"></a>解説

このグローバル変数のメソッドを使用して、Visual C++ 6.0 で提供されている (現在使用されていない) クラス CComModule の機能を提供できます。

### <a name="example"></a>例

```cpp
LONG lLocks = _pAtlModule->GetLockCount();
```

### <a name="requirements"></a>要件

**ヘッダー:** atlbase. h
