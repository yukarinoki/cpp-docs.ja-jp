---
title: 包含ウィンドウの使用
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
- contained windows in ATL
ms.assetid: 7b3d79e5-b569-413f-9b98-df4f14efbe2b
ms.openlocfilehash: 5da765eae28d411c98e79af5b9173f48ea66ef8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329301"
---
# <a name="using-contained-windows"></a>包含ウィンドウの使用

ATL は、含まれているウィンドウを[実装します](../atl/reference/ccontainedwindowt-class.md)。 包含ウィンドウは、メッセージをコンテナー オブジェクトにデリゲートするウィンドウを表し、独自のクラスで処理する代わりにコンテナー オブジェクトにメッセージをデリゲートします。

> [!NOTE]
> 包含ウィンドウを使用するためにクラス`CContainedWindowT`を派生させる必要はありません。

包含ウィンドウでは、既存の Windows クラスをスーパークラス化することも、既存のウィンドウをサブクラス化することもできます。 既存の Windows クラスをスーパークラス化するウィンドウを作成するには、まず、オブジェクトのコンストラクターで既存`CContainedWindowT`のクラス名を指定します。 次に`CContainedWindowT::Create`、 を呼び出します。 既存のウィンドウをサブクラス化するために、Windows クラス名を指定する必要はありません (コンストラクターに NULL を渡します)。 サブクラス化`CContainedWindowT::SubclassWindow`されるウィンドウへのハンドルを使用してメソッドを呼び出すだけです。

通常、コンテナー クラスのデータ メンバーとして、含まれているウィンドウを使用します。 コンテナはウィンドウである必要はありません。ただし[、CMessageMap](../atl/reference/cmessagemap-class.md)から派生する必要があります。

包含ウィンドウは、代替メッセージ・マップを使用して、そのメッセージを処理できます。 複数のウィンドウが含まれている場合は、複数の代替メッセージ マップを宣言し、それぞれに別のウィンドウが含まれているウィンドウに対応するようにします。

## <a name="example"></a>例

次に、2 つのウィンドウが含まれているコンテナー クラスの例を示します。

[!code-cpp[NVC_ATL_Windowing#67](../atl/codesnippet/cpp/using-contained-windows_1.h)]

含まれているウィンドウの詳細については[、SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)サンプルを参照してください。

## <a name="see-also"></a>関連項目

[ウィンドウクラス](../atl/atl-window-classes.md)
