---
title: Platform::ChangedStateException クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
helpviewer_keywords:
- Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
ms.openlocfilehash: 749e242db37944f0c4dcbfb785028b01a0604f14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581680"
---
# <a name="platformchangedstateexception-class"></a>Platform::ChangedStateException クラス

オブジェクトの内部状態が変化したときにスローされ、メソッドの結果を無効にします。

## <a name="syntax"></a>構文

```cpp
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Remarks

この例外がスローされる 1 つの例は、コレクション反復子またはコレクション ビューのメソッドが、親コレクションの変更後に呼び出された場合です。この結果、メソッドの結果は無効になります。

詳細については、 [COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。

### <a name="requirements"></a>必要条件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="see-also"></a>関連項目

[Platform::COMException クラス](../cppcx/platform-comexception-class.md)