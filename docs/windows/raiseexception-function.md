---
title: RaiseException 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
dev_langs:
- C++
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 12032318f898b2986b64d5cd8a1e611a31d1fc8c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372393"
---
# <a name="raiseexception-function"></a>RaiseException 関数

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
inline void __declspec(noreturn)   RaiseException(
      HRESULT hr,
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);
```

### <a name="parameters"></a>パラメーター

*hr*<br/>
中に発生します。 例外の例外コード失敗した操作の HRESULT。

*dwExceptionFlags*<br/>
継続可能の例外 (フラグの値は 0)、または (フラグの値が 0 以外) noncontinuable の例外を示すフラグ。 既定では、例外は、継続不可能は。

## <a name="remarks"></a>Remarks

呼び出し元のスレッドで例外が発生します。

詳細については、Windows を参照してください。`RaiseException`関数。

## <a name="requirements"></a>要件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)