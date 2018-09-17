---
title: Dll の遅延読み込みの制約 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69e985b81072de306c818218e19bbb660e3e04a4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719734"
---
# <a name="constraints-of-delay-loading-dlls"></a>DLL の遅延読み込みの制約

インポートの遅延読み込みには制約があります。

- データのインポートはサポートされません。 その回避策として、`LoadLibrary` (または遅延読み込みヘルパーが DLL を読み込んだことが確認された後は `GetModuleHandle`) および `GetProcAddress` を使用してデータ インポートを自分で明示的に処理します。

- 遅延読み込み Kernel32.dll はサポートされません。 この DLL は、遅延読み込みヘルパー ルーチンが遅延読み込みを実行するのに必要です。

- [バインド](../../build/reference/binding-imports.md)エントリの転送されるポイントはサポートされません。

- 遅延読み込み DLL のエントリ ポイントでプロセスごとに初期化が起こる場合、DLL の遅延読み込みでプロセスの動作が同じにならない可能性があります。 それ以外の場合は、静的 TLS (スレッド ローカル ストレージ) を使用して宣言を含める[_declspec](../../cpp/thread.md)を使用して、DLL が読み込まれるときに処理されません`LoadLibrary`します。 `TlsAlloc`、`TlsFree`、`TlsGetValue`、および `TlsSetValue` を使用した動的 TLS は、静的または遅延読み込み DLL で引き続き利用可能です。

- 静的 (グローバル) 関数ポインターは、関数への最初の呼び出しの後に、インポートされた関数について再初期化する必要があります。 これは、関数ポインターを最初に使用するときにはサンクをポイントするからです。

- 現時点では、通常のインポート メカニズムを使いながら、DLL の特定の手順の読み込みだけを遅延する方法はありません。

- カスタム呼び出し規約 (x86 アーキテクチャでの条件コードの使用など) はサポートされません。 また、浮動小数点レジスタはどのプラットフォームにも保存されません。 カスタム ヘルパー ルーチンまたはフック ルーチンが浮動小数点型を使用する場合、浮動小数点パラメーターのレジスタ呼び出し規約を持つコンピューターで浮動小数点状態を完全に保存およびリストアする必要があります。 ヘルプ関数内の数値データ プロセッサ (NDP) スタックで、浮動小数点パラメーターを取得する CRT 関数を呼び出す場合、CRT DLL の遅延呼び出しに注意します。

## <a name="see-also"></a>関連項目

[リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)<br/>
[LoadLibrary 関数](https://msdn.microsoft.com/library/windows/desktop/ms684175.aspx)<br/>
[GetModuleHandle 関数](https://msdn.microsoft.com/library/windows/desktop/ms683199.aspx)<br/>
[GetProcAddress 関数](https://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)<br/>
[TlsAlloc 関数](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc)<br/>
[TlsFree 関数](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsfree)<br/>
[TlsGetValue 関数](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)<br/>
[TlsSetValue 関数](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)