---
description: 詳細については、「Dll の遅延読み込みの制約」を参照してください。
title: DLL の遅延読み込みの制約
ms.date: 01/19/2021
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.openlocfilehash: 0bc29695aa48fea08a0126d4b814329656a5d3bf
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666980"
---
# <a name="constraints-of-delay-loading-dlls"></a>DLL の遅延読み込みの制約

DLL インポートの遅延読み込みには、いくつかの制約があります。

- データのインポートはサポートされていません。 回避策として、 `LoadLibrary` (または `GetModuleHandle` 遅延読み込みヘルパーが DLL を読み込んだことを確認した後にを使用して) およびを使用して、データのインポートを明示的に処理し `GetProcAddress` ます。

- 遅延読み込みは *`Kernel32.dll`* サポートされていません。 遅延読み込みヘルパールーチンを機能させるには、この DLL を読み込む必要があります。

- 転送されたエントリポイントの[バインド](binding-imports.md)はサポートされていません。

- 起動時に読み込まれるのではなく、DLL が遅延読み込みされた場合、プロセスの動作が異なることがあります。 これは、遅延読み込み DLL のエントリポイントで発生するプロセスごとの初期化がある場合に表示されます。 その他のケースには、を使用して宣言された静的 TLS (スレッドローカルストレージ) があり [`__declspec(thread)`](../../cpp/thread.md) ます。これは、を介して DLL が読み込まれるときに処理されません `LoadLibrary` 。 `TlsAlloc`、`TlsFree`、`TlsGetValue`、および `TlsSetValue` を使用した動的 TLS は、静的または遅延読み込み DLL で引き続き利用可能です。

- 各関数の最初の呼び出しの後に、インポートされた関数への静的グローバル関数ポインターを再初期化します。 これが必要なのは、関数ポインターの最初の使用は、読み込まれた関数ではなくサンクを指しているためです。

- 現時点では、通常のインポートメカニズムを使用しているときに、DLL から特定のプロシージャのみの読み込みを遅延する方法はありません。

- カスタム呼び出し規則 (x86 アーキテクチャでの条件コードの使用など) はサポートされていません。 また、浮動小数点レジスタはどのプラットフォームにも保存されません。 カスタムヘルパールーチンまたはフックルーチンが浮動小数点型を使用する場合、浮動小数点パラメーターでレジスタ呼び出し規約を使用するコンピューターに、完全な浮動小数点の状態を保存して復元する必要があります。 特に、help 関数の数値データプロセッサ (NDP) スタックで浮動小数点パラメーターを受け取る CRT 関数を呼び出す場合は、CRT DLL の遅延読み込みに注意してください。

## <a name="see-also"></a>こちらもご覧ください

[リンカーによる Dll の遅延読み込み](linker-support-for-delay-loaded-dlls.md)\
[`LoadLibrary` プロシージャ](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)\
[`GetModuleHandle` プロシージャ](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlew)\
[`GetProcAddress` プロシージャ](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)\
[`TlsAlloc` プロシージャ](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)\
[`TlsFree` プロシージャ](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsfree)\
[`TlsGetValue` プロシージャ](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)\
[`TlsSetValue` 関数](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)
