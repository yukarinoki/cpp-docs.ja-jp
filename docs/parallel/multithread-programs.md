---
title: マルチ スレッド プログラム |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25debffcd667c7e0d7405d0a4454b60729825fcb
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43131282"
---
# <a name="multithread-programs"></a>マルチスレッド プログラム
スレッドは、基本的に、プログラム実行のパスです。 Win32 のスケジュール実行の最小単位です。 スレッドは、スタック、CPU レジスタ、およびシステムのスケジューラの実行のリスト内のエントリの状態で構成されます。 各スレッドは、プロセスのすべてのリソースを共有します。  
  
プロセスは、1 つまたは複数のスレッドと、コード、データ、およびメモリ内のプログラムの他のリソースで構成されます。 一般的なプログラムのリソースとは、開いているファイル、セマフォ、および動的に割り当てられたメモリです。 プログラムでは、システムのスケジューラがそのスレッドの 1 つ実行制御を実行します。 スケジューラは、どのスレッドが実行するを実行する時期を決定します。 優先順位の低いスレッドは、優先度の高いスレッドがタスクを完了するまで待機する必要があります。 スケジューラは、マルチプロセッサ コンピューターで、CPU 負荷を分散する別のプロセッサの個別のスレッドを移動できます。  
  
プロセス内の各スレッドは独立して動作します。 設定して相互に表示されるが、いないスレッドは個別に実行し、プロセス内の他のスレッドに対応していません。 ただし、共通のリソースを共有するスレッドは、セマフォ、またはプロセス間通信の別のメソッドを使用して作業を調整する必要があります。 スレッドの同期の詳細については、次を参照してください。[マルチ スレッド Win32 プログラムの作成](writing-a-multithreaded-win32-program.md)です。  
  
## <a name="see-also"></a>関連項目  

[C と Win32 を使用するマルチスレッド](multithreading-with-c-and-win32.md)