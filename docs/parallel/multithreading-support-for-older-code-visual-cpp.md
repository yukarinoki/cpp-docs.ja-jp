---
title: 古いコード (Visual C) のためのマルチ スレッドのサポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c911ff2f0dcd43a6f07144f893b91f3a97c6708b
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "42538718"
---
# <a name="multithreading-support-for-older-code-visual-c"></a>旧形式のコードのためのマルチスレッド サポート (Visual C++)
Visual C++ では、並列に実行する複数のスレッドを同時に実行させることができます。 マルチスレッドを使うと、バックグラウンドのタスクを別に分けたり、複数の入力ストリームを同時に管理したり、ユーザー インターフェイスを管理したりできます。  
  
## <a name="in-this-section"></a>このセクションの内容  
 
[C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)  
Microsoft Windows で動作するマルチスレッド アプリケーションの作成方法について説明します。  
  
[C++ と MFC を使用するマルチスレッド](../parallel/multithreading-with-cpp-and-mfc.md)  
プロセスとスレッドについて説明します。また、MFC でマルチスレッドを使用する方法についても説明します。  
  
[マルチスレッドとロケール](../parallel/multithreading-and-locales.md)  
C ランタイム ライブラリとマルチ スレッド アプリケーションでは、C++ 標準ライブラリの両方のロケール機能を使用するときに発生する問題について説明します。  
  
## <a name="related-sections"></a>関連項目  
 
[CWinThread](../mfc/reference/cwinthread-class.md)  
アプリケーション内の実行中のスレッドを表します。  
  
[CSyncObject](../mfc/reference/csyncobject-class.md)  
Win32 の同期オブジェクトに共通の機能を提供する純粋仮想クラスについて説明します。  
  
[CSemaphore](../mfc/reference/csemaphore-class.md)  
セマフォを表します。これは、1 つ以上のプロセスの限られた数のスレッドだけがリソースにアクセスできるようにする同期オブジェクトです。  
  
[CMutex](../mfc/reference/cmutex-class.md)  
ミューテックスを表します。これは、1 つのスレッドがリソースに排他アクセスできるようにする同期オブジェクトです。  
  
[CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
クリティカル セクションを表します。これは、一度に 1 つのスレッドだけがリソースまたはコード セクションにアクセスできるようにする同期オブジェクトです。  
  
[CEvent](../mfc/reference/cevent-class.md)  
イベントを表します。これは、イベントが発生したことを、あるスレッドが別のスレッドに通知できるようにする同期オブジェクトです。  
  
[CMultiLock](../mfc/reference/cmultilock-class.md)  
マルチスレッド プログラムで複数のリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
[CSingleLock](../mfc/reference/csinglelock-class.md)  
マルチスレッド プログラムで 1 つのリソースのアクセス制御に使うアクセス コントロール機構を表します。  