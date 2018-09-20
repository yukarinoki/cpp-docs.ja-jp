---
title: スレッド コントロールのための C ランタイム ライブラリ関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _beginthread function
- _endthread function
- threading [C++], controlling threads
- multithreading [C++], controlling threads
- _beginthreadex function
- _endthreadex function
ms.assetid: 39d0529c-c392-4c6f-94f5-105d1e8054e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a665ee3ec640d84d185d4923e0777f853b187ce6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448130"
---
# <a name="c-run-time-library-functions-for-thread-control"></a>スレッド コントロールのための C ランタイム ライブラリ関数

Win32 プログラムはすべて、スレッドを少なくとも 1 つ持っています。 どのスレッドでも新しいスレッドを作成できます。 スレッドには、作業をすばやく完了して終了するものもあれば、プログラムの実行中アクティブ状態を続けるものもあります。

LIBCMT と MSVCRT の C ランタイム ライブラリは、スレッドの作成および終了のため、次の機能を提供します。 [_beginthread、_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)と[_endthread、_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)します。

`_beginthread` 関数および `_beginthreadex` 関数は、新しいスレッドを作成し、スレッドが正常に作成されるとスレッド識別子を返します。 スレッドは、実行を完了した時点で自動的に終了するか、`_endthread` または `_endthreadex` を呼び出すことによってそのスレッド自体を終了します。

> [!NOTE]
> Libcmt.lib を使用してビルドしたプログラムから C ランタイム ルーチンを呼び出す場合は、`_beginthread` 関数または `_beginthreadex` 関数でスレッドを起動する必要があります。 Win32 の `ExitThread` 関数および `CreateThread` 関数は使用しないでください。 また、C ランタイム ライブラリのデータ構造体へアクセス中のスレッドがあって、その完了を待っている複数のスレッドが存在する場合に `SuspendThread` を使うと、デッドロック状態になります。

##  <a name="_core_the__beginthread_function"></a> _Beginthread および _beginthreadex 関数

`_beginthread` 関数および `_beginthreadex` 関数は、新しいスレッドを作成します。 スレッドは、プロセスのコードやデータ セグメントをプロセス内の他のスレッドと共有しますが、各スレッドには、独自のレジスタ値、スタック領域、および現在の命令アドレスがあります。 それぞれのスレッドに CPU 時間が与えられるので、プロセス中のすべてのスレッドを同時に実行できます。

`_beginthread` `_beginthreadex`に似ていますが、 [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) Win32 api 関数が、これらの違い。

- これらの関数は、特定の C ランタイム ライブラリ変数を初期化します。 これは、スレッドで C ランタイム ライブラリを使う場合に重要です。

- `CreateThread` は、セキュリティ属性を制御します。 CreateThread を使うと、一時的に停止状態になっているスレッドの実行を再開できます。

`_beginthread` および `_beginthreadex` は、正常に終了した場合は新しいスレッドのハンドルを、エラーが発生した場合はエラー コードをそれぞれ返します。

##  <a name="_core_the__endthread_function"></a> _Endthread、_endthreadex 関数

[_Endthread](../c-runtime-library/reference/endthread-endthreadex.md)関数によって作成されたスレッドを終了します`_beginthread`(同様に、`_endthreadex`によって作成されたスレッドを終了します`_beginthreadex`)。 これらの関数が終了すると、スレッドは自動的に終了します。 `_endthread` および `_endthreadex` は、スレッドの内部条件に基づいて終了させる場合に便利です。 たとえば、通信ポートを制御できないときに、通信処理専用のスレッドを終了する場合があります。

## <a name="see-also"></a>関連項目

[C と Win32 を使用するマルチスレッド](multithreading-with-c-and-win32.md)