---
title: ODBC クラスおよびスレッド
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: 8cb5df605bef31e177e976798f975bb4ca14ced7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213179"
---
# <a name="odbc-classes-and-threads"></a>ODBC クラスおよびスレッド

MFC 4.2 以降では、MFC ODBC クラスに対するマルチスレッドサポートがあります。 ただし、MFC では DAO クラスのマルチスレッドサポートは提供されないことに注意してください。

ODBC クラスのマルチスレッドサポートにはいくつかの制限があります。 これらのクラスは ODBC API をラップするため、これらのクラスは、それらが構築されるコンポーネントのマルチスレッドサポートに限定されます。 たとえば、多くの ODBC ドライバーはスレッドセーフではありません。そのため、これらのドライバーのいずれかを使用している場合、MFC ODBC クラスはスレッドセーフではありません。 特定のドライバーがスレッドセーフであるかどうかを確認する必要があります。

マルチスレッドアプリケーションを作成する場合は、複数のスレッドを使用して同じオブジェクトを操作することに注意する必要があります。 たとえば、2つのスレッドで同じ `CRecordset` オブジェクトを使用すると、データを取得するときに問題が発生する可能性があります。1つのスレッドでフェッチ操作を行うと、他のスレッドでフェッチされたデータが上書きされることがあります。 個別のスレッドでの MFC ODBC クラスの一般的な使用方法は、スレッド間で開いている `CDatabase` オブジェクトを共有し、同じ ODBC 接続を使用し、各スレッドで個別の `CRecordset` オブジェクトを使用することです。 開かれていない `CDatabase` オブジェクトを別のスレッドの `CRecordset` オブジェクトに渡すことはできないことに注意してください。

> [!NOTE]
>  複数のスレッドで同じオブジェクトを操作する必要がある場合は、重要なセクションなどの適切な同期メカニズムを実装する必要があります。 `Open`などの特定の操作は保護されていないことに注意してください。 これらの操作は、個別のスレッドから同時に呼び出されないようにする必要があります。

マルチスレッドアプリケーションの作成の詳細については、「[マルチスレッドのトピック](../../parallel/multithreading-support-for-older-code-visual-cpp.md)」を参照してください。

## <a name="see-also"></a>参照

[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[データ アクセス プログラミング (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)
