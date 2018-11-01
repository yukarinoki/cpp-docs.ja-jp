---
title: Platform::InvalidArgumentException クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::InvalidArgumentException
- VCCORLIB/Platform::InvalidArgumentException::InvalidArgumentException
helpviewer_keywords:
- Platform::InvalidArgumentException
ms.assetid: 1a8d860b-3bcb-41a9-9346-6610616a0b46
ms.openlocfilehash: 11b1e0e2166bba2dc366520161729a8d84e865d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643613"
---
# <a name="platforminvalidargumentexception-class"></a>Platform::InvalidArgumentException クラス

メソッドに渡された引数のいずれかが無効な場合にスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class InvalidArgumentException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Remarks

詳細については、 [COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。

### <a name="requirements"></a>必要条件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="see-also"></a>関連項目

[Platform::COMException クラス](../cppcx/platform-comexception-class.md)