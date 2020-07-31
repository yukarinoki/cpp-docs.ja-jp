---
title: /volatile (volatile キーワードの解釈を)
ms.date: 11/04/2016
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
ms.openlocfilehash: 7c2c1cd477b424f56e66bd9246e7bde76ad06120
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223786"
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (volatile キーワードの解釈を)

[Volatile](../../cpp/volatile-cpp.md)キーワードの解釈方法を指定します。

## <a name="syntax"></a>構文

> **/volatile:**{**iso** | **ミリ秒**}

## <a name="arguments"></a>引数

**/volatile: iso**<br/>
**`volatile`** ISO 標準の C++ 言語で定義されている厳密なセマンティクスを選択します。 volatile アクセスでは取得と開放のセマンティックスは保証されていません。 コンパイラが ARM をターゲットとする場合、これはの既定の解釈です **`volatile`** 。

**/volatile: ミリ秒**<br/>
Microsoft 拡張 **`volatile`** セマンティクスを選択します。これにより、ISO 標準の C++ 言語を超えるメモリ順序が保証されます。 volatile アクセスでは取得と開放のセマンティックスは保証されます。 ただし、このオプションにより、コンパイラはハードウェアのメモリ バリアを強制的に生成します。これによって ARM および他のメモリ オーダリングの弱いアーキテクチャでは、著しいオーバーヘッドが追加される場合があります。 コンパイラが ARM 以外のプラットフォームを対象とする場合、これはの既定の解釈です **`volatile`** 。

## <a name="remarks"></a>解説

スレッド間で共有されるメモリを扱う場合は、明示的な同期プリミティブおよびコンパイラの組み込みと共に **/volatile: iso**を使用することを強くお勧めします。 詳細については、「 [volatile](../../cpp/volatile-cpp.md)」を参照してください。

既存のコードを移植する場合、またはプロジェクトの途中でこのオプションを変更する場合は、警告[C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md)を有効にして、セマンティクスの違いによって影響を受けるコードの場所を特定することをお勧めします。

`#pragma` には、このオプションを制御するための相当するものはありません。

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>/volatile コンパイラ オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [**追加オプション**] ボックスで、 **/volatile: iso**また**は/volatile: ms**を追加し、[ **OK]** または [**適用**] を選択して変更を保存します。

## <a name="see-also"></a>関連項目

[volatile](../../cpp/volatile-cpp.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
