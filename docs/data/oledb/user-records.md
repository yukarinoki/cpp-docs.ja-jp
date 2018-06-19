---
title: ユーザー レコード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_MAP
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aea6b4b2ebb1a02e4ef669b437fbe7eb30937f9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109808"
---
# <a name="user-records"></a>ユーザー レコード
静的アクセサーを使用する (から派生したアクセサー **CAccessor)**、コンシューマー ユーザー レコードが存在する必要があります。 ユーザー レコードは、入力を処理または出力のデータ要素を含む C++ クラスです。 ATL OLE DB コンシューマー ウィザードでは、コンシューマーにユーザー レコードが生成されます。 メソッドは、コマンドの処理などのオプションのタスクのユーザー レコードを追加できます。  
  
 次のコードでは、コマンドを処理するサンプル レコードを示します。 ユーザー レコードの`BEGIN_COLUMN_MAP`プロバイダーからコンシューマーに渡されるデータ行セットを表します。 `BEGIN_PARAM_MAP` コマンド パラメーターのセットを表します。 この例では、 [CCommand](../../data/oledb/ccommand-class.md)コマンドのパラメーターを処理するクラス。 マップ エントリのデータ メンバーは、1 つの連続するクラスのインスタンスごとにメモリ ブロックのオフセットを表します。 `COLUMN_ENTRY`マクロに対応している、`PROVIDER_COLUMN_ENTRY`プロバイダー側でマクロです。  
  
 詳細については、 **COLUMN_MAP**と**PARAM_MAP**マクロを参照してください[OLE DB コンシューマー テンプレート用マクロ](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)です。  
  
```  
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
 コンシューマーを生成する ATL OLE DB コンシューマー ウィザードを使用する場合は、OLE DB テンプレートまたは OLE DB 属性を使用する選択肢があります。 生成されたコードは、各ケースで異なります。 このコードの詳細については、次を参照してください。[コンシューマー クラス](../../data/oledb/consumer-wizard-generated-classes.md)です。  
  
## <a name="user-record-support-for-multiple-accessors"></a>ユーザー レコードの複数アクセサーのサポート  
 複数のアクセサーを使用する必要があるシナリオの詳細については、次を参照してください。[行セットでの複数のアクセサーを使用して](../../data/oledb/using-multiple-accessors-on-a-rowset.md)です。  
  
 次の例では、ユーザー レコードが、行セットで複数のアクセサーをサポートするように変更を示します。 代わりに`BEGIN_COLUMN_MAP`と`END_COLUMN_MAP`を使用して[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)と[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)アクセサーごとにします。 `BEGIN_ACCESSOR`マクロは、アクセサーの数 (0 からのオフセット) および、アクセサーが自動でかどうかを指定します。 Autoaccessors 呼び出し`GetData`データへの呼び出しを自動的に取得する[MoveNext](../../data/oledb/crowset-movenext.md)です。 非自動アクセサーでは、明示的にデータを取得する必要があります。 すべてのレコードを取得するたくない (ビットマップ イメージ) のような大規模なデータ フィールドにバインドする場合は、非自動アクセサーを使用します。  
  
```  
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