---
title: Platform::delegate クラス |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
dev_langs:
- C++
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78ac7cce43dbe08097c1e7b78423fadafc7f5309
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101912"
---
# <a name="platformdelegate-class"></a>Platform::Delegate クラス

関数オブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
public delegate void delegate_name();
```

### <a name="members"></a>メンバー

Delegate クラスには、 [Platform::Object Class](../cppcx/platform-object-class.md)から派生した Equals()、GetHashCode()、ToString() メソッドがあります。

### <a name="remarks"></a>Remarks

デリゲートを作成するには [delegate](../windows/delegate-cpp-component-extensions.md) キーワードを使用します。Platform::Delegate を明示的に使用しないでください。 詳細については、「[デリゲート](../cppcx/delegates-c-cx.md)」を参照してください。 作成し、デリゲートを使用する方法の例は、次を参照してください。 [C++ での Windows ランタイム コンポーネントの作成](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)です。

### <a name="requirements"></a>要件

**クライアントがサポートされている最小:** Windows 8

**サポートされているサーバーの最小値:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform.winmd

## <a name="see-also"></a>関連項目

[Platform 名前空間](../cppcx/platform-namespace-c-cx.md)