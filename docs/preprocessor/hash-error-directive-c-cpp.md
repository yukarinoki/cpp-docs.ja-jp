---
description: '詳細情報: #error ディレクティブ (C/c + +)'
title: '#error ディレクティブ (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: fd6503de9590893ee0ec53cbbfa59429a0cfdcfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261152"
---
# <a name="error-directive-cc"></a>#error ディレクティブ (C/c + +)

**#Error** ディレクティブは、コンパイル時にユーザー指定のエラーメッセージを出力し、コンパイルを終了します。

## <a name="syntax"></a>構文

> **#error** *トークン-文字列*

## <a name="remarks"></a>解説

このディレクティブによって出力されるエラーメッセージには、 *トークン文字列* パラメーターが含まれます。 *トークン文字列* パラメーターは、マクロの展開の対象になりません。 このディレクティブは、プリプロセス中、プログラムの不整合を開発者に通知する場合、または制約違反を発生させる場合に最も役立ちます。 次の例は、プリプロセス中のエラーの処理を示しています。

```cpp
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>関連項目

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)
