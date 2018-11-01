---
title: 致命的なエラー C1021
ms.date: 11/04/2016
f1_keywords:
- C1021
helpviewer_keywords:
- C1021
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
ms.openlocfilehash: 35b94e6cea177121c38d06706b42437ec610c38a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587106"
---
# <a name="fatal-error-c1021"></a>致命的なエラー C1021

プリプロセッサ コマンド 'string' が無効です

`string` は無効な [プリプロセッサ ディレクティブ](../../preprocessor/preprocessor-directives.md)です。 エラーを解決するには、 `string`に有効なプリプロセッサ名を使用します。

次の例では C1021 が生成されます。

```
// C1021.cpp
#BadPreProcName    // C1021 delete line
```