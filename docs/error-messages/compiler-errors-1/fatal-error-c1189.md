---
title: 致命的なエラー C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 2217b865109cc48151e4e96b2d38b88764c0c64f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203642"
---
# <a name="fatal-error-c1189"></a>致命的なエラー C1189

> **\#エラー:** *ユーザーが指定したエラーメッセージ*

## <a name="remarks"></a>解説

C1189 は `#error` ディレクティブによって生成されます。 ディレクティブをコードする開発者は、エラーメッセージのテキストを指定します。 詳細については、「 [#error ディレクティブ (C++C/)](../../preprocessor/hash-error-directive-c-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C1189 が生成されます。 このサンプルでは、`_WIN32` 識別子が定義されていないため、開発者はカスタムエラーメッセージを発行します。

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>参照

[#define ディレクティブ (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
