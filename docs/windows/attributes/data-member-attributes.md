---
title: データ メンバーの属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
ms.openlocfilehash: e188f4d9ad2c553ff142e45ec84bc0a04630b816
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512932"
---
# <a name="data-member-attributes"></a>データ メンバー属性

次の属性は、クラス、コクラスまたはインターフェイス内のデータ メンバーに適用されます。

|属性|説明|
|---------------|-----------------|
|[db_accessor](db-accessor.md)|グループ`db_column`に参加している属性`IAccessor`-ベースのバインド。|
|[db_column](db-column.md)|行セットに指定された列をバインドします。|
|[db_command](db-command.md)|OLE DB コマンドを作成します。|
|[db_param](db-param.md)|入力または出力パラメーターを使用して、指定したメンバー変数を関連付けるし、変数を区切ります。|
|[db_source](db-source.md)|データ ソースへの接続を作成します。|
|[db_table](db-table.md)|OLE DB、テーブルを開きます。|
|[defaultbind](defaultbind.md)|オブジェクトを最もよく表す単一のバインド可能なプロパティを示します。|
|[displaybind](displaybind.md)|バインド可能なユーザーに表示されるプロパティを示します。|
|[ID](id.md)|メンバー関数 (プロパティまたはメソッド、インターフェイスまたは dispinterface) のように DISPID を指定します。|
|[range](range-cpp.md)|引数または値を持つが実行時に設定されているフィールドに使用できる値の範囲を指定します。|
|[rdx](rdx.md)|レジストリ キーを作成または既存のレジストリ キーを変更します。|
|[readonly](readonly-cpp.md)|データ メンバーへの割り当てを禁止します。|
|[requestedit](requestedit.md)|プロパティをサポートしていることを示します、`OnRequestEdit`通知します。|

## <a name="see-also"></a>関連項目

[使用法別の属性](attributes-by-usage.md)