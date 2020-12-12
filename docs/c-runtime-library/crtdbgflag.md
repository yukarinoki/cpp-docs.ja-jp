---
description: '詳細については、次を参照してください: _crtDbgFlag'
title: _crtDbgFlag
ms.date: 11/04/2016
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
ms.openlocfilehash: ef3c72b89ea9e5e557a567af9a9c52c8e85370ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246758"
---
# <a name="_crtdbgflag"></a>_crtDbgFlag

**_crtDbgFlag** フラグは、ヒープのデバッグ バージョンでのメモリ割り当てがどのように追跡、検証、報告、およびダンプされるかを制御する 5 つのビット フィールドで構成されます。 このフラグのビット フィールドは、[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して設定されます。 このフラグとそのビット フィールドは、Crtdbg.h で宣言されます。 このフラグは、[_DEBUG](../c-runtime-library/debug.md) フラグがアプリケーションで定義されている場合にのみ使用できます。

このフラグを他のデバッグ機能と組み合わせて使用する方法の詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

## <a name="see-also"></a>関連項目

[制御フラグ](../c-runtime-library/control-flags.md)
