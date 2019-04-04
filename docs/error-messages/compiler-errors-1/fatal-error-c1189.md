---
title: 致命的なエラー C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 06d42316a0109ac063bba43cefebd9aab71c2e72
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565530"
---
# <a name="fatal-error-c1189"></a>致命的なエラー C1189

> **\#エラー:** *ユーザーが指定したエラー メッセージ*

## <a name="remarks"></a>Remarks

C1189 がによって生成された、`#error`ディレクティブ。 ディレクティブをコード開発者には、エラー メッセージのテキストを指定します。 詳細については、[#error ディレクティブ (c/c++)](../../preprocessor/hash-error-directive-c-cpp.md)を参照してください。

## <a name="example"></a>例

次の例では、C1189 が生成されます。 ため、サンプルでは、開発者がカスタム エラー メッセージを発行、`_WIN32`識別子が定義されていません。

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>関連項目

[#define ディレクティブ (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)