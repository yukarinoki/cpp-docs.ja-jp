---
title: _ _Asm ブロックでの C または C++ シンボルの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 746614de653649747bf20ae4c223e5687ee53f5c
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049428"
---
# <a name="using-c-or-c-symbols-in-asm-blocks"></a>__asm ブロックでの C または C++ シンボルの使用
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `__asm`ブロックは、ブロックが表示されるスコープ内の C または C++ シンボルを参照できます。 (C および C++ のシンボルは、変数名、関数名、およびラベルである、シンボリック定数のない名前または`enum`メンバー。 できません C++ メンバー関数を呼び出します。)  
  
 C および C++ の記号を使用するいくつかの制限が適用されます。  
  
-   各アセンブリ言語のステートメントには、1 つの C または C++ シンボルのみを含めることができます。 複数のシンボルは、同じアセンブリ命令だけに現れる**長さ**、**型**、および**サイズ**式。  
  
-   参照される関数、`__asm`ブロックは (プロトタイプ) プログラムの前に宣言する必要があります。 それ以外の場合、コンパイラと区別できない関数名のラベル、`__asm`ブロックします。  
  
-   `__asm`ブロック (ケース) に関係なく予約 MASM 単語と同じスペル チェックですべての C または C++ シンボルは使用できません。 MASM の予約語などの命令名**プッシュ**SI などの名前を登録します。  
  
-   構造体と共用体のタグがで認識されない`__asm`ブロックします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)