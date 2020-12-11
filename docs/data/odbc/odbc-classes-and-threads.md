---
description: 詳細については、「ODBC クラスとスレッド」を参照してください。
title: ODBC クラスおよびスレッド
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
ms.openlocfilehash: bff5ef5a53543b2e0ffa7888f469ed4ce1e54a37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161079"
---
# <a name="odbc-classes-and-threads"></a>ODBC クラスおよびスレッド

MFC 4.2 以降では、MFC ODBC クラスに対するマルチスレッドサポートがあります。 ただし、MFC では DAO クラスのマルチスレッドサポートは提供されないことに注意してください。

ODBC クラスのマルチスレッドサポートにはいくつかの制限があります。 これらのクラスは ODBC API をラップするため、これらのクラスは、それらが構築されるコンポーネントのマルチスレッドサポートに限定されます。 たとえば、多くの ODBC ドライバーはスレッドセーフではありません。そのため、これらのドライバーのいずれかを使用している場合、MFC ODBC クラスはスレッドセーフではありません。 特定のドライバーがスレッドセーフであるかどうかを確認する必要があります。

マルチスレッドアプリケーションを作成する場合は、複数のスレッドを使用して同じオブジェクトを操作することに注意する必要があります。 たとえば、 `CRecordset` 2 つのスレッドで同じオブジェクトを使用すると、データを取得するときに問題が発生する可能性があります。1つのスレッドでフェッチ操作を行うと、他のスレッドでフェッチされたデータが上書きされる可能性があります。 個別のスレッドでの MFC ODBC クラスの一般的な使用方法は、スレッド間で開いているオブジェクトを共有し `CDatabase` て、同じ ODBC 接続を使用し、各スレッドに個別のオブジェクトを使用することです `CRecordset` 。 開かれていない `CDatabase` オブジェクトを `CRecordset` 別のスレッドのオブジェクトに渡すことはできないことに注意してください。

> [!NOTE]
> 複数のスレッドで同じオブジェクトを操作する必要がある場合は、重要なセクションなどの適切な同期メカニズムを実装する必要があります。 などの特定の操作は保護されていないことに注意して `Open` ください。 これらの操作は、個別のスレッドから同時に呼び出されないようにする必要があります。

マルチスレッドアプリケーションの作成の詳細については、「 [マルチスレッドのトピック](../../parallel/multithreading-support-for-older-code-visual-cpp.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[データアクセスプログラミング (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)
