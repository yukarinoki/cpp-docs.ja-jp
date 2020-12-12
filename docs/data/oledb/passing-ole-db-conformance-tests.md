---
description: 詳細については、OLE DB 準拠テストを渡す
title: OLE DB 準拠合致テスト
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
ms.openlocfilehash: d2a5b788b3a118293800b02a9383fbde9845cfa5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286724"
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB 準拠合致テスト

プロバイダーの一貫性を高めるために、データアクセス SDK には一連の OLE DB 準拠テストが用意されています。 テストでは、プロバイダーのすべての側面を確認し、プロバイダーが期待どおりに機能することを合理的に保証します。 OLE DB 適合テストについては、Microsoft Data Access SDK を参照してください。 このセクションでは、準拠テストに合格するために必要な作業について説明します。 OLE DB 準拠テストの実行の詳細については、SDK を参照してください。

## <a name="running-the-conformance-tests"></a>準拠テストの実行

Visual C++ 6.0 では、OLE DB プロバイダーテンプレートに、値とプロパティを確認できるようにするフック関数がいくつか追加されています。 これらの関数のほとんどは、準拠テストへの応答として追加されました。

> [!NOTE]
> OLE DB 準拠テストに渡すには、プロバイダーに対していくつかの検証関数を追加する必要があります。

このプロバイダーには、2つの検証ルーチンが必要です。 最初のルーチンは、 `CRowsetImpl::ValidateCommandID` 行セットクラスの一部です。 プロバイダーテンプレートによって行セットが作成されるときに呼び出されます。 このサンプルでは、このルーチンを使用して、インデックスがサポートされていないことをコンシューマーに通知します。 最初の呼び出しはです `CRowsetImpl::ValidateCommandID` (プロバイダーは `_RowsetBaseClass` ブックマークをサポートするためにのインターフェイスマップに追加された typedef を使用し `CCustomRowset` ます。そのため、テンプレート引数の長い行を入力する必要はありません)。 [](../../data/oledb/provider-support-for-bookmarks.md) 次に、インデックスパラメーターが NULL でない場合に DB_E_NOINDEX を返します (これは、コンシューマーが私のためにインデックスを使用することを示します)。 コマンド Id の詳細については、OLE DB の仕様を参照してください `IOpenRowset::OpenRowset` 。

次のコードは、 `ValidateCommandID` 検証ルーチンです。

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H
// Class: CCustomRowset

HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)
{
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);
   if (hr != S_OK)
      return hr;

   if (pIndexID != NULL)
      return DB_E_NOINDEX;    // Doesn't support indexes

   return S_OK;
}
```

プロバイダーテンプレートは、 `OnPropertyChanged` ユーザーが DBPROPSET_ROWSET グループのプロパティを変更するたびにメソッドを呼び出します。 他のグループのプロパティを処理する場合は、適切なオブジェクトに追加します (つまり、DBPROPSET_SESSION によってクラスにチェックインされ `CCustomSession` ます)。

このコードは、まず、プロパティが別のにリンクされているかどうかを確認します。 プロパティがチェーンされている場合は、DBPROP_BOOKMARKS プロパティがに設定され `True` ます。 OLE DB 仕様の付録 C には、プロパティに関する情報が含まれています。 また、この情報は、プロパティが別のプロパティにチェーンされているかどうかも示します。

また、ルーチンをコードに追加することもでき `IsValidValue` ます。 テンプレートは、 `IsValidValue` プロパティを設定しようとしたときにを呼び出します。 プロパティ値を設定するときに追加の処理が必要な場合は、このメソッドをオーバーライドします。 これらのメソッドのいずれかをプロパティセットごとに設定できます。

## <a name="see-also"></a>関連項目

[高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)
