---
title: C と Win32 でのマルチ スレッド |Microsoft Docs
ms.custom: ''
ms.date: 02/02/2018
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09397b5a60dcc2cbe2b3e6265f6080f3c5c1e212
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428097"
---
# <a name="multithreading-with-c-and-win32"></a>C と Win32 を使用するマルチスレッド

Microsoft Visual C では、マルチ スレッド アプリケーションを作成するためのサポートを提供します。 複数のスレッドを使用して、アプリケーションがユーザー インターフェイスが応答しなくなる原因となる負荷の高い操作を実行する必要がある場合を検討してください。

Visual C++ では、複数のスレッドを含むプログラムを作成する方法として、MFC (Microsoft Foundation Class) ライブラリを使用する方法と、C ランタイム ライブラリと Win32 API を使用する方法の 2 つがあります。 MFC でマルチ スレッド アプリケーションを作成する方法の詳細については、次を参照してください[C++ と MFC を使用するマルチ スレッド](multithreading-with-cpp-and-mfc.md)c 言語でのマルチ スレッドに関する次のトピックを読む。

以下のトピックでは、マルチスレッド プログラムの作成をサポートする Visual C++ の機能について説明します。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [どのようなマルチ スレッドの詳細については、](multithread-programs.md)

- [ライブラリのサポートのマルチ スレッド](library-support-for-multithreading.md)

- [インクルード ファイルのマルチ スレッド](include-files-for-multithreading.md)

- [スレッド コントロールのための C ランタイム ライブラリ関数](c-run-time-library-functions-for-thread-control.md)

- [C のサンプルのマルチ スレッド プログラム](sample-multithread-c-program.md)

- [マルチ スレッド Win32 プログラムの作成](writing-a-multithreaded-win32-program.md)

- [コンパイルとリンクのマルチ スレッド プログラム](compiling-and-linking-multithread-programs.md)

- [マルチ スレッド プログラムの問題を回避](avoiding-problem-areas-with-multithread-programs.md)

- [スレッド ローカル ストレージ (TLS)](thread-local-storage-tls.md)

## <a name="see-also"></a>関連項目

[旧形式のコードのためのマルチスレッド サポート (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)