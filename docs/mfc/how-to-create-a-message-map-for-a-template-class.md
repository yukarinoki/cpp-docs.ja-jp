---
description: '詳細については、「方法: テンプレートクラスのメッセージマップを作成する」を参照してください。'
title: '方法 : テンプレート クラスのメッセージ マップを作成する'
ms.date: 11/04/2016
helpviewer_keywords:
- template classes [MFC], creating message maps
- message maps [MFC], template classes
ms.assetid: 4e7e24f8-06df-4b46-82aa-7435c8650de3
ms.openlocfilehash: 16d1d486bae77d0e580521ba71d29216701c4481
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253430"
---
# <a name="how-to-create-a-message-map-for-a-template-class"></a>方法 : テンプレート クラスのメッセージ マップを作成する

MFC のメッセージマッピングは、Windows メッセージを適切な C++ オブジェクトインスタンスに転送するための効率的な方法を提供します。 MFC メッセージマップのターゲットの例としては、アプリケーションクラス、ドキュメントクラスとビュークラス、コントロールクラスなどがあります。

従来の MFC メッセージマップは、メッセージマップの開始を宣言するために [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) マクロを使用して宣言され、各メッセージハンドラークラスメソッドのマクロエントリ、最後に [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) マクロによってメッセージマップの末尾を宣言します。

[BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map)マクロの1つの制限は、テンプレート引数を含むクラスと組み合わせて使用した場合に発生します。 テンプレートクラスと共に使用する場合、マクロの展開中にテンプレートパラメーターがないため、このマクロはコンパイル時エラーを発生させます。 [BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)マクロは、1つのテンプレート引数を含むクラスが独自のメッセージマップを宣言できるように設計されています。

## <a name="example"></a>例

たとえば、MFC の [CListBox](reference/clistbox-class.md) クラスが拡張され、外部データソースとの同期が実現されているとします。 架空の `CSyncListBox` クラスは次のように宣言されます。

[!code-cpp[NVC_MFC_CListBox#42](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_1.h)]

クラスは、 `CSyncListBox` 同期されるデータソースを記述する単一の型でテンプレート化されます。 また、クラスのメッセージマップに参加する3つのメソッド (、、) も宣言し `OnPaint` `OnDestroy` `OnSynchronize` ます。 `OnSynchronize`メソッドは次のように実装されます。

[!code-cpp[NVC_MFC_CListBox#43](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_2.cpp)]

上記の実装では `CSyncListBox` 、、、など、メソッドを実装する任意のクラス型でクラスを特殊化でき `GetCount` `CArray` `CList` `CMap` ます。 `StringizeElement`関数は、次の方法でプロトタイプが宣言されたテンプレート関数です。

[!code-cpp[NVC_MFC_CListBox#44](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_3.cpp)]

通常、このクラスのメッセージマップは次のように定義されます。

```cpp
BEGIN_MESSAGE_MAP(CSyncListBox, CListBox)
  ON_WM_PAINT()
  ON_WM_DESTROY()
  ON_MESSAGE(LBN_SYNCHRONIZE, OnSynchronize)
END_MESSAGE_MAP()
```

ここで **LBN_SYNCHRONIZE** は、アプリケーションによって定義されたカスタムユーザーメッセージです。次に例を示します。

[!code-cpp[NVC_MFC_CListBox#45](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_4.cpp)]

上記のマクロマップはコンパイルされません。これは、 `CSyncListBox` マクロの展開時にクラスのテンプレートの仕様が見つからないためです。 **BEGIN_TEMPLATE_MESSAGE_MAP** マクロは、指定されたテンプレートパラメーターを展開されたマクロマップに組み込むことによってこれを解決します。 このクラスのメッセージマップは次のようになります。

[!code-cpp[NVC_MFC_CListBox#46](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_5.cpp)]

オブジェクトを使用したクラスの使用例を次に示し `CSyncListBox` `CStringList` ます。

[!code-cpp[NVC_MFC_CListBox#47](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_6.cpp)]

テストを完了するには、 `StringizeElement` クラスを使用するように関数を特殊化する必要があり `CStringList` ます。

[!code-cpp[NVC_MFC_CListBox#48](codesnippet/cpp/how-to-create-a-message-map-for-a-template-class_7.cpp)]

## <a name="see-also"></a>関連項目

[BEGIN_TEMPLATE_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_template_message_map)<br/>
[メッセージの処理とマッピング](message-handling-and-mapping.md)
