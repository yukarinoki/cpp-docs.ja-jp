---
title: naked 関数呼び出し
ms.date: 11/04/2016
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
ms.openlocfilehash: f9d8a8747d4a808d040b814005782ed8187bf274
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301579"
---
# <a name="naked-function-calls"></a>naked 関数呼び出し

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

宣言された関数、 **naked**属性を使用して、独自のカスタム プロローグとエピローグ シーケンスを記述できるように、プロローグまたはエピローグのコードがなくても出力されます、[インライン アセンブラー](../assembler/inline/inline-assembler.md)します。 naked 関数は高度な機能です。 これにより、C/C++ 以外のコンテキストから呼び出される関数を宣言して、パラメーターの存在する場所や保持されるレジスタについて、異なる想定をすることができます。 例としては、割り込みハンドラーのようなルーチンが挙げられます。 この機能は、仮想デバイス ドライバー (VxD) を作成するときに特に便利です。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [naked](../cpp/naked-cpp.md)

- [naked 関数に関する規則と制限](../cpp/rules-and-limitations-for-naked-functions.md)

- [プロローグ/エピローグ コードの記述に関する考慮事項](../cpp/considerations-for-writing-prolog-epilog-code.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[呼び出し規約](../cpp/calling-conventions.md)