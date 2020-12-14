---
description: '詳細情報: RaiseException 関数'
title: RaiseException 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: b5353757ff04ab12c0fc61da6b2e98b2df835ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198441"
---
# <a name="raiseexception-function"></a>RaiseException 関数

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
inline void __declspec(noreturn)   RaiseException(
      HRESULT hr,
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);
```

### <a name="parameters"></a>パラメーター

*時間*<br/>
発生している例外の例外コード。つまり、失敗した操作の HRESULT です。

*dwExceptionFlags*<br/>
継続不可能な例外 (フラグ値がゼロ)、または継続不可能な例外 (フラグ値が0以外) を示すフラグ。 既定では、例外は継続不可能です。

## <a name="remarks"></a>解説

呼び出し元のスレッドで例外を発生させます。

詳細については、「Windows 関数」を参照してください `RaiseException` 。

## <a name="requirements"></a>要件

**ヘッダー:** 内部 .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>関連項目

[Microsoft:: WRL::D etails 名前空間](microsoft-wrl-details-namespace.md)
