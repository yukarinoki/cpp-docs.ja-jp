---
title: 致命的なエラー C1099 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1099
dev_langs:
- C++
helpviewer_keywords:
- C1099
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5c975960310136729620ae8304364667f6e8e60
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045043"
---
# <a name="fatal-error-c1099"></a>致命的なエラー C1099

エディット コンティニュ エンジンはコンパイルを終了しています。

エディット コンティニュはコード変更をコンパイルする準備としてプリコンパイル済みヘッダー ファイルを読み込みましたが、その後のアクション (プリコンパイル済みヘッダーの `#include` ステートメントの前のコード変更、またはデバッガーの停止など) により、エディット コンティニュはこのプロセスでコンパイルを完了できませんでした。 このエラーを解決するために操作を実行する必要はありません。