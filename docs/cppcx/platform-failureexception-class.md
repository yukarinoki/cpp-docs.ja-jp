---
description: '詳細情報: Platform:: FailureException クラス'
title: Platform::FailureException クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::FailureException::FailureException
- VCCORLIB/Platform::FailureException
helpviewer_keywords:
- Platform::FailureException
ms.assetid: 1729cd07-bfc2-448e-9db5-185d5cbf5b81
ms.openlocfilehash: 0b3f03888a92cc0c52e347ce5ee663a3e57b0b20
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161261"
---
# <a name="platformfailureexception-class"></a>Platform::FailureException クラス

操作が失敗したときにスローされます。 これは E_FAIL HRESULT と同等です。

## <a name="syntax"></a>構文

```cpp
public ref class FailureException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>解説

詳細については、 [COMException](../cppcx/platform-comexception-class.md) クラスを参照してください。

### <a name="requirements"></a>要件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform. winmd

## <a name="see-also"></a>関連項目

[Platform:: COMException クラス](../cppcx/platform-comexception-class.md)
