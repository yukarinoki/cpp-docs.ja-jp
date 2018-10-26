---
title: 'ODBC: ODBC データ ソースの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources, configuring
- ODBC connections, configuring
- configuring ODBC data sources
ms.assetid: 1cd03e6a-8d59-4eca-a8c6-1010582d5e67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9a0cd385596f62432f16b7e5abc4259a267dd76
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080313"
---
# <a name="odbc-configuring-an-odbc-data-source"></a>ODBC: ODBC データ ソースの設定

使用する、[データソース](../../data/odbc/data-source-odbc.md)開発したアプリケーションには、それを構成する ODBC アドミニストレーターを使用する必要があります。 Odbc データ ソース アドミニストレーターの使用可能なデータ ソースとその接続情報を Windows レジストリの追跡。 ODBC アドミニストレーターを使用して、追加、変更、およびデータ ソースの削除、**データソース**] ダイアログ ボックスを追加および ODBC ドライバーを削除します。

> [!NOTE]
>  この情報は、ODBC へのアクセスの MFC データ アクセス オブジェクト (DAO) クラスを使用して MFC ODBC クラスを使用するときに適用されます。

ODBC アドミニストレーターには、Microsoft Foundation Classes (MFC) ライブラリのデータベースのサポートが自動的にインストールされます。 Odbc データ ソース アドミニストレーターの詳細については、次を参照してください。 [ODBC アドミニストレーター](../../data/odbc/odbc-administrator.md)とオンラインの ODBC API リファレンスのヘルプ システムです。

MFC データベース アプリケーション用の ODBC セットアップおよび管理プログラムを作成する方法については[テクニカル ノート 48:](../../mfc/tn048-writing-odbc-setup-and-administration-programs.md)します。

## <a name="see-also"></a>関連項目

[ODBC の基礎](../../data/odbc/odbc-basics.md)<br/>
[ODBC: ODBC API 関数の直接呼び出し](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)