---
description: 詳細については、「ODBC コンポーネントを顧客に再配布する」を参照してください。
title: ODBC の構成要素の配布
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
ms.openlocfilehash: 02840156d648507065e0cadb1b8fa2b9c8146a7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204317"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>ODBC の構成要素の配布

ODBC 管理者プログラムの機能をアプリケーションに組み込む場合は、これらのプログラムを実行するファイルもユーザーに配布する必要があります。 これらの ODBC ファイルは Visual C++ CD-ROM の \OS\System ディレクトリに格納されています。 Redistrb ファイルと、同じディレクトリ内の使用許諾契約書には、再配布できる ODBC ファイルの一覧が含まれています。

出荷予定の ODBC ドライバーについては、ドキュメントを参照してください。 どの Dll およびその他のファイルを配布するかを決定する必要があります。 ODBC コンポーネントを再配布する方法については、「 [お客様への Odbc コンポーネント](../../data/odbc/redistributing-odbc-components-to-your-customers.md)の再配布」も参照してください。

また、ほとんどの場合、他の1つのファイルを含める必要があります。 Odbccr32.dll は ODBC カーソルライブラリです。 このライブラリは、レベル1のドライバーに、順方向および逆方向のスクロール機能を提供します。 また、スナップショットをサポートする機能も提供します。 ODBC カーソルライブラリの詳細については、「 [odbc: Odbc カーソルライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)」を参照してください。

次のトピックでは、ODBC をデータベースクラスと共に使用する方法について詳しく説明します。

- [ODBC: ODBC カーソルライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC: ODBC データソースの構成](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC: ODBC API 関数の直接呼び出し](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>関連項目

[ODBC の基礎](../../data/odbc/odbc-basics.md)<br/>
[ODBC 管理者](../../data/odbc/odbc-administrator.md)
