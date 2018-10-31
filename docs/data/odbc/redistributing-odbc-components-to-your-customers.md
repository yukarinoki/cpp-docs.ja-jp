---
title: お客様の ODBC コンポーネントの再配布 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9b28d743b933caab5a017d89b636a78fd8890c10
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069491"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>ODBC の構成要素の配布

Odbc データ ソース アドミニストレーターの機能をアプリケーションに組み込む場合必要がありますもファイルを配布する、ユーザーに、これらのプログラムを実行しています。 これらの ODBC ファイルは、ビジュアルの C++ CD-ROM の \OS\System ディレクトリにあります。 Redistrb.wri ファイルと同じディレクトリにライセンス契約 再配布する ODBC ファイルの一覧が含まれます。

付属する ODBC ドライバーのマニュアルを参照してください。 出荷するには、Dll とその他のファイルを決定する必要があります。 お読みください[お客様への ODBC コンポーネントの再配布](../../data/odbc/redistributing-odbc-components-to-your-customers.md)、ODBC コンポーネントを再配布する方法を説明しています。

さらに、ほとんどの場合にその他の 1 つのファイルを含める必要があります。 Odbccr32.dll は、ODBC カーソル ライブラリです。 このライブラリは、レベル 1 のドライバーの前方と後方スクロール機能を示します。 スナップショットのサポート機能も提供します。 ODBC カーソル ライブラリの詳細については、次を参照してください。 [ODBC: ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)します。

ODBC を使用して、データベース クラスの詳細については、以下のトピックです。

- [ODBC: ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC: ODBC データ ソースの設定](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC: ODBC API 関数の直接呼び出し](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>関連項目

[ODBC の基礎](../../data/odbc/odbc-basics.md)<br/>
[ODBC データ ソース アドミニストレーター](../../data/odbc/odbc-administrator.md)