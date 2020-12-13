---
description: 詳細については、IDispEventSimpleImpl の使用に関するページをご覧ください。
title: IDispEventSimpleImpl の使用 (ATL)
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
ms.openlocfilehash: c0b3f6a0ecdcaae084d3f5d62c19745ee15ac6e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138165"
---
# <a name="using-idispeventsimpleimpl"></a>IDispEventSimpleImpl の使用

を使用してイベントを処理する場合 `IDispEventSimpleImpl` は、次の操作を行う必要があります。

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)からクラスを派生させます。

- イベントシンクマップをクラスに追加します。

- イベントを記述する [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) 構造体を定義します。

- [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info)マクロを使用して、イベントシンクマップにエントリを追加します。

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

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]

この例で実際に使用されているタイプライブラリの情報は、Word オブジェクトの CLSID `Application` とインターフェイスの IID だけです `ApplicationEvents` 。 この情報は、コンパイル時にのみ使用されます。

次のコードは、単純な .h に記述されています。 関連するコードは、コメントによって示されます。

[!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]

次のコードは、単純な .cpp からのものです。

[!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]

## <a name="see-also"></a>関連項目

[イベント処理](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling サンプル](../overview/visual-cpp-samples.md)
