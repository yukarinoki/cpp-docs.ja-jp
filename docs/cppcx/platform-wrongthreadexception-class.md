---
title: Platform::WrongThreadException クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WrongThreadException
- VCCORLIB/Platform::WrongThreadException::WrongThreadException
helpviewer_keywords:
- Platform::WrongThreadException
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
ms.openlocfilehash: b59191eb739a94f305b656425ee2f3725815c7b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639999"
---
# <a name="platformwrongthreadexception-class"></a>Platform::WrongThreadException クラス

スレッドが、スレッドのアパートメントに属さないプロキシ オブジェクト用のインターフェイス ポインターを通じて呼び出すときにスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Remarks

詳細については、 [COMException](../cppcx/platform-comexception-class.md)を参照してください。

### <a name="requirements"></a>必要条件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="see-also"></a>関連項目

[Platform::COMException クラス](../cppcx/platform-comexception-class.md)