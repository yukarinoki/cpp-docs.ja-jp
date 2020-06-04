---
title: CCustomCommand (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidercommand
- ccustomcommand
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderCommand class in MyProviderRS.H
- CCustomCommand class in CustomRS.H
ms.assetid: b30b956e-cc91-4cf5-9fe6-f8b1ce9cc2a5
ms.openlocfilehash: afa8571173117a23962eb84f6fa5b4cf2c3c46e7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211758"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

`CCustomCommand` クラスは、プロバイダーコマンドオブジェクトの実装です。 `IAccessor`、`ICommandText`、および `ICommandProperties` インターフェイスの実装を提供します。 `IAccessor` インターフェイスは、行セットのインターフェイスと同じです。 Command オブジェクトは、アクセサーを使用してパラメーターのバインドを指定します。 行セットオブジェクトでは、出力列のバインドを指定するために使用されます。 `ICommandText` インターフェイスは、コマンドを自由に指定するのに便利な方法です。 この例では、後でカスタムコードを追加するときに `ICommandText` インターフェイスを使用します。また、`ICommand::Execute` メソッドもオーバーライドします。 `ICommandProperties` インターフェイスは、コマンドおよび行セットオブジェクトのすべてのプロパティを処理します。

```cpp
// CCustomCommand
class ATL_NO_VTABLE CCustomCommand :
class ATL_NO_VTABLE CCustomCommand :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IAccessorImpl<CCustomCommand>,
   public ICommandTextImpl<CCustomCommand>,
   public ICommandPropertiesImpl<CCustomCommand>,
   public IObjectWithSiteImpl<CCustomCommand>,
   public IConvertTypeImpl<CCustomCommand>,
   public IColumnsInfoImpl<CCustomCommand>
```

`IAccessor` インターフェイスは、コマンドおよび行セットで使用されるすべてのバインドを管理します。 コンシューマーは、`DBBINDING` 構造体の配列を使用して `IAccessor::CreateAccessor` を呼び出します。 各 `DBBINDING` 構造体には、列のバインドを処理する方法 (型や長さなど) に関する情報が含まれています。 プロバイダーは、構造体を受け取り、データの転送方法と変換が必要かどうかを決定します。 コマンドオブジェクトでは、コマンド内の任意のパラメーターを処理するために、`IAccessor` インターフェイスが使用されます。

Command オブジェクトは、`IColumnsInfo`の実装も提供します。 OLE DB には `IColumnsInfo` インターフェイスが必要です。 インターフェイスを使用すると、コンシューマーはコマンドからパラメーターに関する情報を取得できます。 行セットオブジェクトは、`IColumnsInfo` インターフェイスを使用して、出力列に関する情報をプロバイダーに返します。

プロバイダーには、`IObjectWithSite`と呼ばれるインターフェイスも含まれています。 `IObjectWithSite` インターフェイスは ATL 2.0 で実装されており、実装者はそれ自体に関する情報をその子に渡すことができます。 Command オブジェクトは、`IObjectWithSite` 情報を使用して、生成されたすべての行セットオブジェクトを作成したユーザーについて通知します。

## <a name="see-also"></a>参照

[プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)
