---
title: コンパイラの警告 (レベル 1) C4025 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4025
dev_langs:
- C++
helpviewer_keywords:
- C4025
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 109f1694f63488c167e51c7c2c89675411b6d269
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045576"
---
# <a name="compiler-warning-level-1-c4025"></a>コンパイラの警告 (レベル 1) C4025

'number': _based ポインターが可変引数を伴う関数に渡されました。パラメーター番号

可変個の引数のある関数に _based ポインターを渡すと、ポインターが正規化され、予期しない結果が発生します。 可変個の引数のある関数に _based ポインターを渡さないでください。