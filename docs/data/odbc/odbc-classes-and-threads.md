---
title: ODBC クラスおよびスレッド
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: aaf54a3a1d616cde5742dad45955bd415f612d60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368685"
---
# <a name="odbc-classes-and-threads"></a>ODBC クラスおよびスレッド

MFC 4.2 以降では、MFC ODBC クラスのマルチスレッドのサポートがあります。 ただし、MFC では DAO クラスのマルチスレッドサポートは提供されません。

ODBC クラスのマルチスレッドサポートには、いくつかの制限があります。 これらのクラスは ODBC API をラップするため、ビルドされるコンポーネントのマルチスレッドサポートに制限されます。 たとえば、多くの ODBC ドライバはスレッド セーフではありません。したがって、MFC ODBC クラスをこれらのドライバーのいずれかで使用する場合、スレッド セーフではありません。 特定のドライバーがスレッド セーフかどうかを確認する必要があります。

マルチスレッド アプリケーションを作成する場合は、複数のスレッドを使用して同じオブジェクトを操作する場合は、十分に注意する必要があります。 たとえば、2 つのスレッド`CRecordset`で同じオブジェクトを使用すると、データを取得するときに問題が発生する可能性があります。一方のスレッドでフェッチ操作を行う場合、もう一方のスレッドでフェッチされたデータが上書きされる場合があります。 MFC ODBC クラスを別々のスレッドで使用する一般的な用途`CDatabase`は、開いているオブジェクトをスレッド間で共有し、各`CRecordset`スレッドで個別のオブジェクトを使用して、同じ ODBC 接続を使用することです。 開`CDatabase`いていないオブジェクトを別のスレッドの`CRecordset`オブジェクトに渡す必要はありません。

> [!NOTE]
> 複数のスレッドが同じオブジェクトを操作する必要がある場合は、クリティカル セクションなどの適切な同期メカニズムを実装する必要があります。 などの`Open`特定の操作は保護されないことに注意してください。 これらの操作が、別々のスレッドから同時に呼び出されないようにする必要があります。

マルチスレッド アプリケーションの作成の詳細については、「[マルチスレッド化のトピック」を参照してください](../../parallel/multithreading-support-for-older-code-visual-cpp.md)。

## <a name="see-also"></a>関連項目

[データベース接続を開く (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[データ アクセス プログラミング (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)
