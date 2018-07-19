---
title: setjmp longjump |Microsoft ドキュメント
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
ms.openlocfilehash: 55cf6a2503367777464f09f92e3e3614c3d9f11b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379836"
---
# <a name="setjmplongjump"></a>setjmp/longjump
Setjmpex.h または setjmp.h を含めると、すべての呼び出し[setjmp](../c-runtime-library/reference/setjmp.md)または[longjmp](../c-runtime-library/reference/longjmp.md)デストラクターを呼び出すし、最後に呼び出されをアンワインドが発生します。  これは、プロセスは、finally 句の setjmp.h とデストラクターを呼び出さない x86 とは異なります。  
  
 呼び出し`setjmp`現在のスタック ポインター、非 volatile レジスタと MxCsr レジスタに保持されます。  呼び出す`longjmp`、一番最近に戻る`setjmp`呼び出しサイトのリセット、スタック ポインター、非 volatile レジスタと MxCsr レジスタ、状態に戻すように、最新では保持されます`setjmp`呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)