---
title: -揮発性 (volatile キーワードの解釈) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
dev_langs:
- C++
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccd36c5edaaab8577e5f278b25b51ce69e0633f1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378198"
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (volatile キーワードの解釈を)

指定する方法、[揮発性](../../cpp/volatile-cpp.md)キーワードの解釈します。

## <a name="syntax"></a>構文

> **/volatile:**{**iso**|**ms**}  

## <a name="arguments"></a>引数

**/volatile:iso**  
ISO 標準の C++ 言語で定義されている、厳密な `volatile` のセマンティックスを選択します。 volatile アクセスでは取得と開放のセマンティックスは保証されていません。 コンパイラが ARM をターゲットとする場合は、これは `volatile` の既定の解釈です。

**/volatile:ms**  
Microsoft 拡張 `volatile` セマンティクスを選択すると、ISO 標準 C++ 言語を超えることを保証するメモリ オーダリングが追加されます。 volatile アクセスでは取得と開放のセマンティックスは保証されます。 ただし、このオプションにより、コンパイラはハードウェアのメモリ バリアを強制的に生成します。これによって ARM および他のメモリ オーダリングの弱いアーキテクチャでは、著しいオーバーヘッドが追加される場合があります。 コンパイラが ARM 以外のプラットフォームをターゲットとする場合は、これは `volatile` の既定の解釈です。

## <a name="remarks"></a>コメント

使用することを強くお勧め **/volatile:iso**および明示的な同期プリミティブとコンパイラ組み込み関数はスレッド間で共有されるメモリを扱うときにします。 詳細については、次を参照してください。[揮発性](../../cpp/volatile-cpp.md)です。

既存のコードを移植プロジェクトの途中でこのオプションを変更するか、することが警告を有効にする[C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md)セマンティクスの違いによって影響を受けるコードの場所を識別します。

`#pragma` には、このオプションを制御するための相当するものはありません。

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>/volatile コンパイラ オプションを Visual Studio で設定するには

1. 開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. **追加オプション**ボックスで、追加 **/volatile:iso**または **/volatile:ms**を選択し**OK**または**適用**して変更を保存します。

## <a name="see-also"></a>関連項目

[volatile](../../cpp/volatile-cpp.md)  
[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
