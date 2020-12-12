---
description: '詳細情報: 致命的なエラー C1189'
title: 致命的なエラー C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 4e71903c6567aedf85de81db59b66e45684d8507
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123592"
---
# <a name="fatal-error-c1189"></a>致命的なエラー C1189

> **\# エラー:** ユーザーが指定した *エラーメッセージ*

## <a name="remarks"></a>解説

C1189 は、ディレクティブによって生成され `#error` ます。 ディレクティブをコードする開発者は、エラーメッセージのテキストを指定します。 詳細については、「 [#error ディレクティブ (C/c + +)](../../preprocessor/hash-error-directive-c-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C1189 が生成されます。 このサンプルでは、識別子が定義されていないため、開発者はカスタムエラーメッセージを発行し `_WIN32` ます。

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>関連項目

[#define ディレクティブ (C/c + +)](../../preprocessor/hash-define-directive-c-cpp.md)
