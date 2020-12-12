---
description: '詳細情報: 生関数の呼び出し'
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
ms.openlocfilehash: ffc28b65a8c16881164805f0cfa55ffe1bc54e9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313802"
---
# <a name="naked-function-calls"></a>naked 関数呼び出し

**Microsoft 固有の仕様**

属性を使用して宣言 **`naked`** された関数は、プロローグまたはエピローグコードなしで生成されるため、 [インラインアセンブラー](../assembler/inline/inline-assembler.md)を使用して独自のカスタムプロローグ/エピローグシーケンスを記述できます。 naked 関数は高度な機能です。 これにより、C/C++ 以外のコンテキストから呼び出される関数を宣言して、パラメーターの存在する場所や保持されるレジスタについて、異なる想定をすることができます。 例としては、割り込みハンドラーのようなルーチンが挙げられます。 この機能は、仮想デバイス ドライバー (VxD) を作成するときに特に便利です。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [naked](../cpp/naked-cpp.md)

- [生関数の規則と制限](../cpp/rules-and-limitations-for-naked-functions.md)

- [プロローグ/エピローグコードの記述に関する考慮事項](../cpp/considerations-for-writing-prolog-epilog-code.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[呼び出し規約](../cpp/calling-conventions.md)
