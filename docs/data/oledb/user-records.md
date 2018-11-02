---
title: ユーザー レコード
ms.date: 10/22/2018
f1_keywords:
- COLUMN_ENTRY_MAP
helpviewer_keywords:
- rowsets [C++], accessors
- COLUMN_ENTRY macro
- COLUMN_ENTRY_MAP macro
- user records, OLE DB consumer templates
- OLE DB consumer templates, user records
- CAccessor class, example
- BEGIN_ACCESSOR_MAP macro
- accessors [C++], rowsets
- accessors [C++], static
- BEGIN_ACCESSOR macro, example
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
ms.openlocfilehash: 4d52c36368b9b39815cbb9a103f84f140626ba2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567441"
---
# <a name="user-records"></a>ユーザー レコード

静的アクセサーを使用する (から派生したアクセサー `CAccessor`)、コンシューマーはユーザー レコードが存在する必要があります。 ユーザー レコードは、ハンドルの入力または出力するデータ要素を含む C++ クラスです。 **ATL OLE DB コンシューマー ウィザード**コンシューマー ユーザー レコードが生成されます。 メソッドは、コマンドの処理などのオプションのタスクのユーザー レコードを追加できます。

次のコードでは、コマンドを処理するサンプル レコードを示します。 ユーザーのレコードでは、BEGIN_COLUMN_MAP は、プロバイダーからコンシューマーに渡されるデータ行セットを表します。 BEGIN_PARAM_MAP では、コマンド パラメーターのセットを表します。 この例では、 [CCommand](../../data/oledb/ccommand-class.md)コマンドのパラメーターを処理するクラス。 マップ エントリのデータ メンバーは、1 つの連続したクラスのインスタンスごとにメモリ ブロックのオフセットを表します。 COLUMN_ENTRY マクロは、プロバイダー側で PROVIDER_COLUMN_ENTRY マクロに対応します。

COLUMN_MAP と PARAM_MAP マクロの詳細については、次を参照してください。 [OLE DB コンシューマー テンプレート用マクロ](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)します。

```cpp
class CArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_COLUMN_MAP(CArtists)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
   COLUMN_ENTRY(3, m_nAge)
END_COLUMN_MAP()

// Parameter binding map
BEGIN_PARAM_MAP(CArtists)
   COLUMN_ENTRY(1, m_nAge)
END_PARAM_MAP()
};
```

## <a name="wizard-generated-user-records"></a>ウィザードで生成されたユーザー レコード

使用する場合、 **ATL OLE DB コンシューマー ウィザード**OLE DB テンプレートまたは OLE DB 属性を使用する選択肢があるコンシューマーを生成します。 生成されたコードでは、各ケースで異なります。 このコードの詳細については、次を参照してください。[コンシューマー クラス](../../data/oledb/consumer-wizard-generated-classes.md)します。

## <a name="user-record-support-for-multiple-accessors"></a>複数のアクセサーのユーザー レコードのサポート

複数のアクセサーを使用する必要があるシナリオの詳細については、次を参照してください。[行セットでの複数のアクセサーを使用して](../../data/oledb/using-multiple-accessors-on-a-rowset.md)します。

次の例では、行セットに対して複数のアクセサーをサポートするように変更するユーザー レコードを示します。 BEGIN_COLUMN_MAP と END_COLUMN_MAP、代わりに使用して[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)と[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)各アクセサー。 BEGIN_ACCESSOR マクロでは、アクセサーの数 (0 からのオフセット) および、アクセサーが自動でかどうかを指定します。 Autoaccessors 呼び出し`GetData`への呼び出しで自動的にデータを取得する[MoveNext](../../data/oledb/crowset-movenext.md)します。 非自動アクセサーでは、明示的にデータを取得する必要があります。 すべてのレコードを取得するたくない (ビットマップ イメージなどの大規模なデータ フィールドにバインドしている場合は、非自動アクセサーを使用します。

```cpp
class CMultiArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor
    COLUMN_ENTRY(1, m_szFirstName)
    COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor
    COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)