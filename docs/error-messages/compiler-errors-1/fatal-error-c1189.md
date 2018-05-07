---
title: 致命的なエラー C1189 |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 051b7eb965526d12311dfacaeae7a00e4fbe4e75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1189"></a>致命的なエラー C1189

> **\#エラー:** *ユーザーが指定したエラー メッセージ*

## <a name="remarks"></a>コメント

C1189 がによって生成された、`#error`ディレクティブです。 ディレクティブをコード開発者は、エラー メッセージのテキストを指定します。 詳細については、次を参照してください。 [#error ディレクティブ (c/c++)](../../preprocessor/hash-error-directive-c-cpp.md)です。

## <a name="example"></a>例

次の例では、C1189 を生成します。 サンプルでは、開発者がカスタム エラー メッセージを発行、`_WIN32`識別子が定義されていません。

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>関連項目

[#define ディレクティブ (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)