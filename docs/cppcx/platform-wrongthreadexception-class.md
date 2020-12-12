---
description: '詳細情報: Platform:: WrongThreadException クラス'
title: Platform::WrongThreadException クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WrongThreadException
- VCCORLIB/Platform::WrongThreadException::WrongThreadException
helpviewer_keywords:
- Platform::WrongThreadException
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
ms.openlocfilehash: a7fbaed7766a3928ca24d56f5233c38d9298d466
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307731"
---
# <a name="platformwrongthreadexception-class"></a>Platform::WrongThreadException クラス

スレッドが、スレッドのアパートメントに属さないプロキシ オブジェクト用のインターフェイス ポインターを通じて呼び出すときにスローされます。

## <a name="syntax"></a>構文

```cpp
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>解説

詳細については、 [COMException](../cppcx/platform-comexception-class.md)を参照してください。

### <a name="requirements"></a>要件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform. winmd

## <a name="see-also"></a>関連項目

[Platform:: COMException クラス](../cppcx/platform-comexception-class.md)
