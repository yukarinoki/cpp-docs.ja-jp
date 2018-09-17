---
title: setjmp longjump |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f53160a5deeb3ea0db111fc0aae7429b19b7cc86
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703275"
---
# <a name="setjmplongjump"></a>setjmp/longjump

呼び出す setjmpex.h または setjmp.h を含めると、 [setjmp](../c-runtime-library/reference/setjmp.md)または[longjmp](../c-runtime-library/reference/longjmp.md)アンワインドするデストラクターを呼び出すし、最後になります。  これは、プロセスは、setjmp.h の finally 句とデストラクターを呼び出さない、x86 とは異なります。

呼び出し`setjmp`現在のスタック ポインター、非 volatile レジスタ、および MxCsr レジスタに保持されます。  呼び出す`longjmp`最新に戻り`setjmp`呼び出しサイトとリセット スタック ポインター、非 volatile レジスタ、および MxCsr レジスタ、状態に戻すように、最新では保持されます`setjmp`呼び出します。

## <a name="see-also"></a>関連項目

[呼び出し規則](../build/calling-convention.md)