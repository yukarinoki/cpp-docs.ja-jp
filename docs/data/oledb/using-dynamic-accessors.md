---
title: 動的アクセサーの使用
ms.date: 10/18/2018
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
ms.openlocfilehash: 4f42d6f20da819cf325cad06a04878b46e52352a
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008674"
---
# <a name="using-dynamic-accessors"></a>動的アクセサーの使用

動的アクセサーを使用すると、データベーススキーマ (基になる構造) に関する知識がなくても、データソースにアクセスできます。 OLE DB テンプレートライブラリには、支援するクラスがいくつか用意されています。

[Dynamicconsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)サンプルでは、動的アクセサークラスを使用して、列情報を取得し、アクセサーを動的に作成する方法を示します。

## <a name="using-cdynamicaccessor"></a>CDynamicAccessor の使用

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) を使用すると、データベーススキーマ (データベースの基になる構造) に関する知識がなくても、データソースにアクセスできます。 `CDynamicAccessor` メソッドは、列名、カウント、データ型などの列情報を取得します。 この列情報は、実行時にアクセサーを動的に作成するために使用します。 列情報は、このクラスによって作成および管理されるバッファーに格納されます。 [GetValue](./cdynamicaccessor-class.md#getvalue)メソッドを使用してバッファーからデータを取得します。

## <a name="example-cdynamic-accessors"></a>例: CDynamic アクセサー

```cpp
// Using_Dynamic_Accessors.cpp
// compile with: /c /EHsc
#include <stdio.h>
#include <objbase.h>
#include <atldbcli.h>

int main(int argc, char* argv[] )
{
    HRESULT hr = CoInitialize(NULL );

    CDataSource ds;
    CSession ss;

    CTable<CDynamicAccessor> rs;

    // The following is an example initialization string:
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"
      L"Integrated Security=SSPI;Persist Security Info=False;"
      L"Initial Catalog=Loginname;Data Source=your_data_source;"
      L"Use Procedure for Prepare=1;Auto Translate=True;"
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"
      L"Use Encryption for Data=False;"
      L"Tag with column collation when possible=False");

    hr = ss.Open(ds );
    hr = rs.Open(ss, "Shippers" );

    hr = rs.MoveFirst();
    while(SUCCEEDED(hr ) && hr != DB_S_ENDOFROWSET )
    {
        for(size_t i = 1; i <= rs.GetColumnCount(); i++ )
        {
            DBTYPE type;
            rs.GetColumnType(i, &type );
            printf_s( "Column %d [%S] is of type %d\n",
                      i, rs.GetColumnName(i ), type );

            switch(type )
            {
                case DBTYPE_WSTR:
                    printf_s( "value is %S\n",
                              (WCHAR*)rs.GetValue(i ) );
                break;
                case DBTYPE_STR:
                    printf_s( "value is %s\n",
                              (CHAR*)rs.GetValue(i ) );
                default:
                    printf_s( "value is %d\n",
                              *(long*)rs.GetValue(i ) );
            }
        }
        hr = rs.MoveNext();
    }

    rs.Close();
    ss.Close();
    ds.Close();
    CoUninitialize();

    return 0;
}
```

## <a name="using-cdynamicstringaccessor"></a>CDynamicStringAccessor の使用

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) は、1つの重要な方法を除いて、 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)のように機能します。 は `CDynamicAccessor` プロバイダーによって報告されたネイティブ形式のデータを要求しますが、は、 `CDynamicStringAccessor` データストアからアクセスされるすべてのデータを文字列データとして取得するようにプロバイダーに要求します。 このプロセスは、データストアのコンテンツの表示や印刷など、データストアの値の計算を必要としない単純なタスクに特に便利です。

`CDynamicStringAccessor`列情報を取得するには、メソッドを使用します。 この列情報は、実行時にアクセサーを動的に作成するために使用します。 列情報は、このクラスによって作成および管理されるバッファーに格納されます。 [CDynamicStringAccessor:: GetString](./cdynamicstringaccessor-class.md#getstring)を使用してバッファーからデータを取得するか、 [CDynamicStringAccessor:: setstring](./cdynamicstringaccessor-class.md#setstring)を使用してバッファーに格納します。

## <a name="example-cdynamicstringaccessor"></a>例: CDynamicStringAccessor

```cpp
// Using_Dynamic_Accessors_b.cpp
// compile with: /c /EHsc
#include <stdio.h>
#include <objbase.h>
#include <atldbcli.h>

int main(int argc, char* argv[] )
{
    HRESULT hr = CoInitialize(NULL );
    if (hr != S_OK)
    {
        exit (-1);
    }

    CDataSource ds;
    CSession ss;

    CTable<CDynamicStringAccessor> rs;

    // The following is an example initialization string:
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"
      L"Integrated Security=SSPI;Persist Security Info=False;"
      L"Initial Catalog=Loginname;Data Source=your_data_source;"
      L"Use Procedure for Prepare=1;Auto Translate=True;"
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"
      L"Use Encryption for Data=False;"
      L"Tag with column collation when possible=False");

    hr = ss.Open(ds );
    hr = rs.Open(ss, "Shippers" );

    hr = rs.MoveFirst();
    while(SUCCEEDED(hr ) && hr != DB_S_ENDOFROWSET )
    {
        for(size_t i = 1; i <= rs.GetColumnCount(); i++ )
        {
            printf_s( "column %d value is %s\n",
                      i, rs.GetString(i ) );
        }
        hr = rs.MoveNext();
    }

    rs.Close();
    ss.Close();
    ds.Close();
    CoUninitialize();

   return 0;
}
```

## <a name="using-cdynamicparameteraccessor"></a>CDynamicParameterAccessor の使用

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) は [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)に似ていますが、 `CDynamicParameterAccessor` [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) インターフェイスを呼び出すことによって設定されるパラメーター情報を取得する点が異なります。 コンシューマーがこのクラスを使用するには、プロバイダーで `ICommandWithParameters` がサポートされている必要があります。

パラメーター情報は、このクラスによって作成および管理されるバッファーに格納されます。 [CDynamicParameterAccessor:: GetParam](./cdynamicparameteraccessor-class.md#getparam)と[CDynamicParameterAccessor:: getparamtype](./cdynamicparameteraccessor-class.md#getparamtype)を使用して、バッファーからパラメーターデータを取得します。

このクラスを使用して SQL Server のストアドプロシージャを実行し、出力パラメーターの値を取得する方法を示す例については、GitHub の[Microsoft VCSamples](https://github.com/Microsoft/VCSamples)リポジトリにある[dynamicconsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)サンプルコードを参照してください。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)<br/>
[CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[DynamicConsumer サンプル](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)
