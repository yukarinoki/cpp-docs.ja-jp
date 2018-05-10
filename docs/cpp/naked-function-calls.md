---
title: Naked 関数の呼び出し |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- virtual device drivers
- VXD virtual device drivers
- virtual device drivers, naked function calls
- naked functions
- prolog code
- epilog code
- naked keyword [C++]
- naked keyword [C++], storage-class attribute
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9d7b42f08d68af9838bf908efdbcc59a0540b91
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="naked-function-calls"></a>naked 関数呼び出し
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 宣言された関数、`naked`を使用して、独自のカスタム プロローグとエピローグ シーケンスを記述できるように、プロローグまたはエピローグのコードがない属性が出力されます、[インライン アセンブラー](../assembler/inline/inline-assembler.md)です。 naked 関数は高度な機能です。 これにより、C/C++ 以外のコンテキストから呼び出される関数を宣言して、パラメーターの存在する場所や保持されるレジスタについて、異なる想定をすることができます。 例としては、割り込みハンドラーのようなルーチンが挙げられます。 この機能は、仮想デバイス ドライバー (VxD) を作成するときに特に便利です。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [naked 関数に関する規則と制限](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [プロローグ/エピローグ コードの記述に関する考慮事項](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規約](../cpp/calling-conventions.md)