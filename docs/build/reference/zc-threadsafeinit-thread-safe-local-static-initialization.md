---
description: '詳細については、/Zc: threadSafeInit (スレッドセーフなローカル静的初期化) に関するページを参照してください。'
title: '/Zc: threadSafeInit (スレッドセーフなローカル静的初期化)'
ms.date: 03/14/2018
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
ms.openlocfilehash: ac14e7979d2adab0b21229f426e00a489c14f38f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271214"
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/Zc: threadSafeInit (スレッドセーフなローカル静的初期化)

**/Zc: threadSafeInit** コンパイラオプションは、静的ローカル (関数スコープ) 変数をスレッドセーフな方法で初期化するようにコンパイラに指示します。これにより、手動での同期が不要になります。 初期化のみがスレッドセーフです。 複数のスレッドによる静的ローカル変数の使用および変更は、それでも手動で同期する必要があります。 このオプションは、Visual Studio 2015 以降で使用できます。 既定では、Visual Studio によってこのオプションが有効になります。

## <a name="syntax"></a>構文

> **/Zc: threadSafeInit**[ **-** ]

## <a name="remarks"></a>解説

C++ 11 標準では、静的またはスレッドストレージ存続期間を持つブロックスコープ変数は、他の初期化が行われる前にゼロ初期化する必要があります。 初期化は、コントロールが変数の宣言を通過すると発生します。 初期化中に例外がスローされた場合、変数は初期化されていないと見なされ、次に制御が宣言を通過したときに初期化が再試行されます。 コントロールが初期化と同時に宣言に入った場合、初期化の完了中に同時実行がブロックされます。 初期化中にコントロールが宣言を再帰的に再入力した場合、動作は未定義になります。 既定では、visual studio 2015 以降の Visual Studio では、この標準動作が実装されています。 この動作は、 **/zc: threadSafeInit** コンパイラオプションを設定することによって明示的に指定できます。

**/Zc: threadSafeInit** コンパイラオプションは、既定でオンになっています。 [/Permissive-](permissive-standards-conformance.md)オプションは、 **/Zc: threadsafeinit** には影響しません。

静的ローカル変数のスレッドセーフな初期化は、ユニバーサル C ランタイムライブラリ (UCRT) で実装されたコードに依存します。 UCRT への依存関係を回避したり、Visual Studio 2015 より前のバージョンの Visual Studio のスレッドセーフでない初期化動作を維持したりするには、 **/zc: threadSafeInit-** option を使用します。 スレッドセーフが不要であることがわかっている場合は、このオプションを使用して、静的なローカル宣言について少し小さく、より高速なコードを生成します。

スレッドセーフな静的ローカル変数は、スレッドローカルストレージ (TLS) を内部的に使用して、静的が既に初期化されている場合に効率的な実行を実現します。 この機能の実装は、windows Vista 以降のオペレーティングシステムでの Windows オペレーティングシステムのサポート機能に依存しています。 Windows XP、Windows Server 2003、およびそれ以前のオペレーティングシステムでは、このサポートがないため、効率が向上することはありません。 これらのオペレーティングシステムには、読み込むことができる TLS セクションの数に関する制限もあります。 TLS セクションの制限を超えると、クラッシュが発生する可能性があります。 コードに問題がある場合、特に以前のオペレーティングシステムで実行する必要があるコードでは、 **/zc: threadSafeInit-** を使用してスレッドセーフな初期化コードを無効にします。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成** ] ドロップダウンメニューから、[ **すべての構成**] を選択します。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. **/Zc: threadsafeinit** または **/Zc: threadsafeinit** を含むように "**追加オプション**" プロパティを変更し、[ **OK]** を選択します。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/Zc (準拠)](zc-conformance.md)<br/>
