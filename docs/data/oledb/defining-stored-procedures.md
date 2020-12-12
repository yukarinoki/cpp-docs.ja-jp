---
description: 詳細については、「ストアドプロシージャの定義」を参照してください。
title: ストアド プロシージャの定義
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, syntax
- OLE DB, stored procedures
- stored procedures, defining
- stored procedures, OLE DB
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
ms.openlocfilehash: 52527da031093d82c9d74be5807a5de26f3ee091
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317689"
---
# <a name="defining-stored-procedures"></a>ストアド プロシージャの定義

ストアドプロシージャを呼び出す前に、 [DEFINE_COMMAND](./macros-and-global-functions-for-ole-db-consumer-templates.md#define_command) マクロを使用して、ストアドプロシージャを定義する必要があります。 コマンドを定義すると、はパラメーターマーカーとして疑問符 (?) を使用してパラメーターを表します。

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{INSERT {name, phone} INTO shippers (?,?)}"))
```

このトピックのコード例で使用されている構文 (中かっこの使用) は、SQL Server に固有です。 ストアドプロシージャで使用する構文は、使用するプロバイダーによって異なる場合があります。

次に、パラメーターマップで、コマンドで使用したパラメーターを指定します。パラメーターは、コマンド内での順序に従って一覧表示されます。

```cpp
BEGIN_PARAM_MAP(CMySProcAccessor)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param
END_PARAM_MAP()
```

前の例では、ストアドプロシージャを定義します。 通常、コードを効率的に再利用するために、データベースには、やなどの名前を持つ定義済みストアドプロシージャのセットが含まれてい `Sales by Year` `dt_adduserobject` ます。 SQL Server Enterprise マネージャーを使用して、定義を表示できます。 これらを次のように呼び出し *ます (?* パラメーターは、ストアドプロシージャのインターフェイスによって異なります。

```cpp
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }"))
DEFINE_COMMAND_EX(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }"))
```

次に、コマンドクラスを宣言します。

```cpp
class CMySProc : public CCommand<CAccessor<CMySProcAccessor>>
```

最後に、次のように、でストアドプロシージャを呼び出し `OpenRowset` ます。

```cpp
CSession m_session;

HRESULT OpenRowset()
{
   return CCommand<CAccessor<CMySProcAccessor>>::Open(m_session);
}
```

また、次のように [db_command](../../windows/attributes/db-command.md) データベース属性を使用してストアドプロシージャを定義することもできます。

```cpp
db_command("{ ? = CALL dbo.dt_adduserobject }")
```

## <a name="see-also"></a>関連項目

[ストアドプロシージャの使用](../../data/oledb/using-stored-procedures.md)
