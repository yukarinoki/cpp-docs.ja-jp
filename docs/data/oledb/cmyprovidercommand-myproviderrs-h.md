---
description: 詳細については、CCustomCommand (CustomRS .H) に関するページを参照してください。
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
ms.openlocfilehash: 35b0e1a1628920a85343a52ce4a003302468884b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170504"
---
# <a name="ccustomcommand-customrsh"></a>CCustomCommand (CustomRS.H)

クラスは、 `CCustomCommand` プロバイダーコマンドオブジェクトの実装です。 、、およびの各インターフェイスの実装を提供し `IAccessor` `ICommandText` `ICommandProperties` ます。 この `IAccessor` インターフェイスは、行セット内のインターフェイスと同じです。 Command オブジェクトは、アクセサーを使用してパラメーターのバインドを指定します。 行セットオブジェクトでは、出力列のバインドを指定するために使用されます。 インターフェイスは、 `ICommandText` コマンドを指定するための便利な方法です。 この例では、 `ICommandText` 後でカスタムコードを追加するときにインターフェイスを使用します。メソッドもオーバーライドし `ICommand::Execute` ます。 インターフェイスは、 `ICommandProperties` コマンドおよび行セットオブジェクトのすべてのプロパティを処理します。

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

インターフェイスは、 `IAccessor` コマンドおよび行セットで使用されるすべてのバインドを管理します。 コンシューマーは、 `IAccessor::CreateAccessor` 構造体の配列を使用してを呼び出し `DBBINDING` ます。 各 `DBBINDING` 構造体には、列のバインドを処理する方法 (型や長さなど) に関する情報が含まれています。 プロバイダーは、構造体を受け取り、データの転送方法と変換が必要かどうかを決定します。 コマンド `IAccessor` オブジェクトでは、インターフェイスを使用して、コマンド内の任意のパラメーターを処理します。

Command オブジェクトは、の実装も提供 `IColumnsInfo` します。 OLE DB にはインターフェイスが必要です `IColumnsInfo` 。 インターフェイスを使用すると、コンシューマーはコマンドからパラメーターに関する情報を取得できます。 行セットオブジェクトは、インターフェイスを使用して、 `IColumnsInfo` 出力列に関する情報をプロバイダーに返します。

プロバイダーには、というインターフェイスも含まれてい `IObjectWithSite` ます。 `IObjectWithSite`インターフェイスは ATL 2.0 で実装されており、実装者が自身に関する情報をその子に渡すことができます。 Command オブジェクトは、情報を使用して、生成された `IObjectWithSite` すべての行セットオブジェクトを作成したユーザーについて通知します。

## <a name="see-also"></a>関連項目

[プロバイダー Wizard-Generated ファイル](../../data/oledb/provider-wizard-generated-files.md)
