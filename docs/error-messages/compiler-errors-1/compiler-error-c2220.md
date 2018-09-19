---
title: コンパイラ エラー C2220 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2220
dev_langs:
- C++
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f4179b396e732ceeea20aeb9428d841a357a6d1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051322"
---
# <a name="compiler-error-c2220"></a>コンパイラ エラー C2220

warning treated as error - no object file generated

[/WX](../../build/reference/compiler-option-warning-level.md)すべての警告をエラーとして扱うようにコンパイラに指示します。 エラーが発生したため、オブジェクトまたは実行可能ファイルは生成されませんでした。

このエラー場合にのみ、 **/WX**フラグが設定され、コンパイル時に警告が発生します。 このエラーを解決するには、プロジェクトのすべての警告を除去する必要があります。

### <a name="to-fix-use-one-of-the-following-techniques"></a>解決するには、次のいずれかの手法を使用します。

- プロジェクトの警告の原因となった問題を解決します。

- 下の警告レベルのコンパイルなどを使用して、 **/W3**の代わりに **/W4**します。

- 使用して、[警告](../../preprocessor/warning.md)プラグマを無効にするか、または特定の警告を抑制します。

- 使用しない **/WX**をコンパイルします。