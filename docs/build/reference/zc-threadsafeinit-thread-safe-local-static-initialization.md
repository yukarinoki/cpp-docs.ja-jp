---
title: /Zc:threadSafeInit (スレッド セーフであるローカル静的な初期化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 438ce5ba783f646e9c8e61d9b82999ea936532b4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381149"
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/Zc:threadSafeInit (スレッド セーフであるローカル静的な初期化)

**/Zc:threadSafeInit**コンパイラ オプション (関数スコープ) の静的ローカル変数を手動同期の必要性を排除すること、スレッド セーフな方法で初期化するためにコンパイラに指示します。 のみの初期化は、スレッド セーフです。 使用して複数のスレッドで静的ローカル変数を変更する必要があります引き続きする手動で同期します。 このオプションは、Visual Studio 2015 以降で使用できます。 既定では、Visual Studio は、このオプションを有効します。

## <a name="syntax"></a>構文

> **/Zc:threadSafeInit**[**-**]

## <a name="remarks"></a>コメント

C++ 11 標準で静的ではブロック スコープ変数またはスレッド ストレージ存続期間必要があります 0 で初期化する他の初期化が行われる前にします。 初期化は、コントロールは、まず、変数の宣言を通過するときに発生します。 初期化中に例外がスローされた場合は、変数は、初期化されていないと見なされますの初期化が再実行しようとした時刻の次のコントロールは、宣言を通過します。 場合は、初期化が完了したときに、同時実行ブロックの初期化と同時に、宣言をコントロールに入力します。 コントロールの初期化中に、宣言を再帰的に再入力した場合、動作は定義されません。 既定では、Visual Studio が Visual Studio 2015 以降では、この標準動作を実装します。 この動作を設定して明示的に指定することがあります、 **/Zc:threadSafeInit**コンパイラ オプション。

**/Zc:threadSafeInit**コンパイラ オプションは既定でオンです。 [寛容/-](permissive-standards-conformance.md)オプションには影響しません **/Zc:threadSafeInit**です。

静的ローカル変数のスレッド セーフな初期化は、ユニバーサル C ランタイム ライブラリ (UCRT) に実装されたコードに依存します。 依存関係を避ける、UCRT を表示するかのバージョンの Visual Studio 2015 の前に Visual Studio の非スレッド セーフな初期化の動作を保持するためには、使用、 **/Zc:threadSafeInit-** オプション。 そのスレッドの安全性は不要な場合は、このオプションを使用して、静的ローカル宣言の周囲により若干少なくなります、高速なコードを生成します。

スレッド セーフな静的ローカル変数、静的なは既に初期化されたときに効率的に実行を提供するのにスレッド ローカル ストレージ (TLS) を内部的に使用します。 この機能の実装は、Windows Vista 以降のオペレーティング システムでの Windows オペレーティング システムのサポート機能に依存します。 Windows XP、Windows Server 2003、および以前のオペレーティング システムはありません、このサポートのため、効率性の利点を受け取りません。 これらのオペレーティング システムでは、読み込むことができる TLS セクションの数の下限の制限があります。 TLS を超えるセクション制限では、クラッシュが発生できます。 これは、以前のオペレーティング システムで実行する必要がありますのあるコードでは特に、コードに問題がある場合を使用して **/Zc:threadSafeInit-** スレッド セーフである初期化コードを無効にします。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. **構成**ドロップダウン メニューで、選択**すべて構成**です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Zc:threadSafeInit**または **/Zc:threadSafeInit-** を選択し**OK**です。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
