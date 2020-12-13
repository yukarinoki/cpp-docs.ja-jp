---
description: '詳細情報: 包含ウィンドウの使用'
title: 包含ウィンドウの使用
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
ms.openlocfilehash: 11beb998365a10a8126e37ecbf7388ec6177e659
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138217"
---
# <a name="using-contained-windows"></a>包含ウィンドウの使用

ATL では、 [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md)を使用して包含ウィンドウを実装します。 包含ウィンドウは、そのメッセージを独自のクラスで処理するのではなく、コンテナーオブジェクトにデリゲートするウィンドウを表します。

> [!NOTE]
> 含まれて `CContainedWindowT` いるウィンドウを使用するために、からクラスを派生させる必要はありません。

包含ウィンドウでは、既存の Windows クラスをスーパークラス化するか、既存のウィンドウをサブクラス化することができます。 既存の Windows クラスをスーパークラスにするウィンドウを作成するには、まず、オブジェクトのコンストラクターで既存のクラス名を指定し `CContainedWindowT` ます。 次に、を呼び出し `CContainedWindowT::Create` ます。 既存のウィンドウをサブクラス化するには、Windows クラス名を指定する必要はありません (コンストラクターに NULL を渡します)。 サブクラス化 `CContainedWindowT::SubclassWindow` されているウィンドウへのハンドルを使用してメソッドを呼び出すだけです。

コンテナークラスのデータメンバーとしては、通常、包含ウィンドウを使用します。 コンテナーはウィンドウである必要はありません。ただし、 [CMessageMap](../atl/reference/cmessagemap-class.md)から派生する必要があります。

包含ウィンドウでは、代替メッセージマップを使用してメッセージを処理できます。 複数のウィンドウが含まれている場合は、複数の代替メッセージマップを宣言し、それぞれを個別の包含ウィンドウに対応させる必要があります。

## <a name="example"></a>例

次に、2つの包含ウィンドウを含むコンテナークラスの例を示します。

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

包含ウィンドウの詳細については、 [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) サンプルを参照してください。

## <a name="see-also"></a>関連項目

[ウィンドウクラス](../atl/atl-window-classes.md)
