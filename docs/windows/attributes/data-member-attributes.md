---
title: データメンバー属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
ms.openlocfilehash: f23ca0963c63212ea2a8a70362b8e76fa0819fc7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214878"
---
# <a name="data-member-attributes"></a>データ メンバー属性

クラス、コクラス、またはインターフェイスのデータメンバーには、次の属性が適用されます。

|Attribute|説明|
|---------------|-----------------|
|[db_accessor](db-accessor.md)|`IAccessor`ベースのバインドに参加する `db_column` 属性をグループ化します。|
|[db_column](db-column.md)|指定された列を行セットにバインドします。|
|[db_command](db-command.md)|OLE DB コマンドを作成します。|
|[db_param](db-param.md)|指定されたメンバー変数を入力パラメーターまたは出力パラメーターに関連付けて、その変数を区切ります。|
|[db_source](db-source.md)|データソースへの接続を作成します。|
|[db_table](db-table.md)|OLE DB テーブルを開きます。|
|[defaultbind](defaultbind.md)|オブジェクトを最もよく表す、1つのバインド可能なプロパティを示します。|
|[displaybind](displaybind.md)|バインド可能としてユーザーに表示される必要があるプロパティを示します。|
|[id](id.md)|メンバー関数 (インターフェイスまたはディスパッチインターフェイスのプロパティまたはメソッド) の DISPID を指定します。|
|[range](range-cpp.md)|実行時に値が設定される引数またはフィールドに使用できる値の範囲を指定します。|
|[rdx](rdx.md)|レジストリキーを作成するか、既存のレジストリキーを変更します。|
|[readonly](readonly-cpp.md)|データ メンバーへの割り当てを禁止します。|
|[requestedit](requestedit.md)|`OnRequestEdit` 通知がプロパティでサポートされることを示します。|

## <a name="see-also"></a>参照

[使用法別の属性](attributes-by-usage.md)
