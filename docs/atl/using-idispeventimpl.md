---
description: 詳細については、IDispEventImpl の使用に関するページをご覧ください。
title: IDispEventImpl の使用 (ATL)
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: 4ddab52eeac3c409b32393e8b8b07a85019143c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157179"
---
# <a name="using-idispeventimpl"></a>IDispEventImpl の使用

を使用してイベントを処理する場合 `IDispEventImpl` は、次の操作を行う必要があります。

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md)からクラスを派生させます。

- イベントシンクマップをクラスに追加します。

- [SINK_ENTRY](reference/composite-control-macros.md#sink_entry)または[SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)マクロを使用して、イベントシンクマップにエントリを追加します。

- 処理するメソッドを実装します。

- イベントソースをアドバイスし、アドバイズを中止します。

## <a name="example"></a>例

次の例は、 `DocumentChange` Word の **Application** オブジェクトによって発生するイベントを処理する方法を示しています。 このイベントは、ディスパッチインターフェイスのメソッドとして定義され `ApplicationEvents` ます。

この例は、 [ATLEventHandling サンプル](../overview/visual-cpp-samples.md)からのものです。

```cpp
[ uuid(000209F7-0000-0000-C000-000000000046), hidden ]
dispinterface ApplicationEvents {
properties:
methods:
    [id(0x00000001), restricted, hidden]
    void Startup();

    [id(0x00000002)]
    void Quit();

    [id(0x00000003)]
    void DocumentChange();
};
```

この例では、を使用して `#import` 、Word のタイプライブラリから必要なヘッダーファイルを生成します。 他のバージョンの Word でこの例を使用する場合は、正しい mso dll ファイルを指定する必要があります。 たとえば、Office 2000 では mso9.dll が提供され、OfficeXP は mso.dll を提供します。 このコードは、 *.pch* (Visual Studio 2017 以前の *stdafx.h* ) から単純化されています。

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

次のコードは、NotSoSimple .h に記述されています。 関連するコードは、コメントによって示されます。

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>関連項目

[イベント処理](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling サンプル](../overview/visual-cpp-samples.md)
