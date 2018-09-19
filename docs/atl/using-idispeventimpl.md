---
title: IDispEventImpl (ATL) の使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48afac392d02edfd3d312583642367bc6726e536
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106793"
---
# <a name="using-idispeventimpl"></a>IDispEventImpl の使用

使用する場合`IDispEventImpl`イベントを処理する必要があります。

- クラスを派生[IDispEventImpl](../atl/reference/idispeventimpl-class.md)します。

- クラスにイベント シンク マップを追加します。

- イベント シンク マップを使用するエントリを追加、 [SINK_ENTRY](reference/composite-control-macros.md#sink_entry)または[SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)マクロ。

- 処理したいメソッドを実装します。

- イベント ソースをアドバイズことをお勧めします.

## <a name="example"></a>例

次の例を処理する方法を示しています、`DocumentChange`によって Word のイベントが発生した**アプリケーション**オブジェクト。 このイベントは、メソッドとしてで定義されている、`ApplicationEvents`ディスパッチ インターフェイス。

例は、[コード](../visual-cpp-samples.md)します。  

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

この例では`#import`Word のタイプ ライブラリから必要なヘッダー ファイルを生成します。 Word の他のバージョンでこの例を使用する場合は、正しい mso dll ファイルを指定する必要があります。 たとえば、Office 2000 mso9.dll を提供し、OfficeXP が mso.dll を提供します。 このコードは、stdafx.h から簡素化します。

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

NotSoSimple.h に次のコードが表示されます。 関連するコードは、コメントでされています。

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>関連項目

[イベント処理](../atl/event-handling-and-atl.md)<br/>
[コード](../visual-cpp-samples.md)

