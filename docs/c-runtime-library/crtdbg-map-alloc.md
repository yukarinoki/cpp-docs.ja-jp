---
title: _CRTDBG_MAP_ALLOC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c48095acceefa4bb4852dab18d35284492e7ba0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069405"
---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC

**_CRTDBG_MAP_ALLOC** フラグがアプリケーションのデバッグ バージョンに定義されていると、ヒープ関数の基本バージョンがそのデバッグ バージョンに直接マッピングされます。 このフラグは、マッピングを行うために、Crtdbg.h で使用されます。 このフラグは、[_DEBUG](../c-runtime-library/debug.md) フラグがアプリケーションで定義されている場合にのみ使用できます。

ヒープ関数のデバッグ バージョンと基本バージョンの違いについては、「[Using the Debug Version Versus the Base Version](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」 (デバッグ バージョンと基本バージョンの違い) を参照してください。

## <a name="see-also"></a>参照

[コントロール フラグ](../c-runtime-library/control-flags.md)