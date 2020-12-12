---
description: '詳細情報: bad_function_call クラス'
title: bad_function_call クラス
ms.date: 11/04/2016
f1_keywords:
- functional/std::bad_function_call
helpviewer_keywords:
- bad_function_call class
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
ms.openlocfilehash: 659630874f84ea9e7d164b560408b162f07e1f68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321600"
---
# <a name="bad_function_call-class"></a>bad_function_call クラス

無効な関数呼び出しを報告します。

## <a name="syntax"></a>構文

```cpp
class bad_function_call : public std::exception {};
```

## <a name="remarks"></a>解説

このクラスは、[function クラス](../standard-library/function-class.md)での `operator()` への呼び出しを示すためにスローされる例外を記述します。
