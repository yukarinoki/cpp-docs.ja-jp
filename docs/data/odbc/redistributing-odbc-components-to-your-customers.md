---
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
ms.openlocfilehash: 0d4d3948add665c54be3d3b0596a7a6fc0e414f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212733"
---
# <a name="redistributing-odbc-components-to-your-customers"></a>ODBC の構成要素の配布

ODBC 管理者プログラムの機能をアプリケーションに組み込む場合は、これらのプログラムを実行するファイルもユーザーに配布する必要があります。 これらの ODBC ファイルは、Visual C++ Cd-rom の \OS\System ディレクトリに格納されています。 Redistrb ファイルと、同じディレクトリ内の使用許諾契約書には、再配布できる ODBC ファイルの一覧が含まれています。

出荷予定の ODBC ドライバーについては、ドキュメントを参照してください。 どの Dll およびその他のファイルを配布するかを決定する必要があります。 ODBC コンポーネントを再配布する方法については、「[お客様への Odbc コンポーネント](../../data/odbc/redistributing-odbc-components-to-your-customers.md)の再配布」も参照してください。

また、ほとんどの場合、他の1つのファイルを含める必要があります。 Odbccr32 は、ODBC カーソルライブラリです。 このライブラリは、レベル1のドライバーに、順方向および逆方向のスクロール機能を提供します。 また、スナップショットをサポートする機能も提供します。 ODBC カーソルライブラリの詳細については、「 [odbc: Odbc カーソルライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)」を参照してください。

次のトピックでは、ODBC をデータベースクラスと共に使用する方法について詳しく説明します。

- [ODBC: ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)

- [ODBC: ODBC データ ソースの設定](../../data/odbc/odbc-configuring-an-odbc-data-source.md)

- [ODBC: ODBC API 関数の直接呼び出し](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)

## <a name="see-also"></a>参照

[ODBC の基礎](../../data/odbc/odbc-basics.md)<br/>
[ODBC データ ソース アドミニストレーター](../../data/odbc/odbc-administrator.md)
