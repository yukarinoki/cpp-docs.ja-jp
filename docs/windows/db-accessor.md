---
title: db_accessor |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_accessor
dev_langs:
- C++
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b81e55500a8ff44c887bed592c9472c5a8d3ea1d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874526"
---
# <a name="dbaccessor"></a>db_accessor
グループ**db_column**に参加している属性`IAccessor`-ベースのバインディングです。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *num*  
 アクセサーの数 (0 から始まる整数インデックス) を指定します。 増加にアクセサー番号順は、整数を使用または定義された値を指定する必要があります。  
  
 *auto*  
 アクセサーが自動的に取得されるかどうかを指定するブール値 (**TRUE**)、または取得できません (**FALSE**)。  
  
## <a name="remarks"></a>コメント  
 **db_accessor**の基になる OLE DB アクセサーを定義後続**db_column**と**db_param**同じクラスまたは関数内の属性です。 **db_accessor**使用可能なメンバー レベルが使用されるグループに**db_column** OLE DB に参加している属性`IAccessor`-ベースのバインディングです。 いずれかと組み合わせて使用されます、 **db_table**または**db_command**属性。 この属性を呼び出すことが呼び出しに似ています、 [BEGIN_ACCESSOR](../data/oledb/begin-accessor.md)と[END_ACCESSOR](../data/oledb/end-accessor.md)マクロです。  
  
 **db_accessor**行セットを生成し、対応するアクセサー マップにバインドします。 呼び出さない場合**db_accessor**アクセサー 0 は自動的に生成され、すべての列バインドは、このアクセサー ブロックにマップされます。  
  
 **db_accessor**グループ データベースの 1 つまたは複数のアクセサーに列のバインド。 複数のアクセサーを使用する必要があるシナリオの詳細については、次を参照してください。[行セットでの複数のアクセサーを使用して](../data/oledb/using-multiple-accessors-on-a-rowset.md)です。 表示されている「ユーザー レコードのサポートの複数のアクセサー」[ユーザー レコード](../data/oledb/user-records.md)です。  
  
 コンシューマー属性プロバイダーは、クラスにこの属性を適用する場合、コンパイラの名前は変更するクラス\_*すると*アクセサー、場所*すると*指定した名前は、クラス、および、コンパイラと呼ばれるクラスを作成また*すると*から派生した\_*すると*アクセサー。  クラス ビューでは、両方のクラスが表示されます。  
  
## <a name="example"></a>例  
 次の例で**db_accessor** Orders テーブルの 2 つのアクセサーに Northwind データベースからのグループ列にします。 アクセサー 0、自動アクセサーは、アクセサー 1 です。  
  
```  
// cpp_attr_ref_db_accessor.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include <atlbase.h>  
#include <atldbcli.h>  
  
[ db_command(L"SELECT LastName, FirstName FROM Orders") ]  
class CEmployees {  
public:  
   [ db_accessor(0, TRUE) ];  
   [ db_column("1") ] LONG m_OrderID;  
   [ db_column("2") ] TCHAR m_CustomerID[6];  
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;   
  
   [ db_accessor(1, FALSE) ];  
   [ db_column("8") ] CURRENCY m_Freight;  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|属性ブロック|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)   
