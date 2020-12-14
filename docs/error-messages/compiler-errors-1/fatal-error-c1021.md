---
description: '詳細情報: 致命的なエラー C1021'
title: 致命的なエラー C1021
ms.date: 11/04/2016
f1_keywords:
- C1021
helpviewer_keywords:
- C1021
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
ms.openlocfilehash: 74998b7b745ab2c0404ecea3392750b71cd40c6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316350"
---
# <a name="fatal-error-c1021"></a>致命的なエラー C1021

プリプロセッサ コマンド 'string' が無効です

`string` が有効な [プリプロセッサディレクティブ](../../preprocessor/preprocessor-directives.md)ではありません。 エラーを解決するには、 `string`に有効なプリプロセッサ名を使用します。

次の例では C1021 が生成されます。

```cpp
// C1021.cpp
#BadPreProcName    // C1021 delete line
```
