---
title: 'MFC ActiveX コントロール : シリアル化'
ms.date: 09/12/2018
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
helpviewer_keywords:
- MFC ActiveX controls [MFC], version support
- wVerMinor global constant [MFC]
- GetVersion method [MFC]
- ExchangeVersion method [MFC]
- MFC ActiveX controls [MFC], serializing
- DoPropExchange method [MFC]
- versioning ActiveX controls
- wVerMajor global constant
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
ms.openlocfilehash: d804486b612906f537b6ed1665dfc0cec5149826
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364550"
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX コントロール : シリアル化

この資料では、ActiveX コントロールをシリアル化する方法について説明します。 シリアル化とは、ディスク ファイルなどの永続ストレージ メディアから読み取りまたは書き込みを行うプロセスです。 MFC (MFC) ライブラリには、クラス内のシリアル化のサポートが`CObject`組み込まれています。 `COleControl`このサポートは、プロパティ交換メカニズムを使用して ActiveX コントロールに拡張されます。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールのシリアル化は[、:D オーバーライド](../mfc/reference/colecontrol-class.md#dopropexchange)することによって実装されます。 この関数は、コントロール オブジェクトの読み込みと保存中に呼び出され、メンバー変数またはメンバー変数で実装されたすべてのプロパティを変更通知とともに格納します。

次のトピックでは、ActiveX コントロールのシリアル化に関連する主な問題について説明します。

- コントロール`DoPropExchange`オブジェクトをシリアル化する関数の実装

- [シリアル化プロセスのカスタマイズ](#_core_customizing_the_default_behavior_of_dopropexchange)

- [バージョン サポートの実装](#_core_implementing_version_support)

## <a name="implementing-the-dopropexchange-function"></a><a name="_core_implementing_the_dopropexchange_function"></a>関数を実装する

ActiveX コントロール ウィザードを使用してコントロール プロジェクトを生成すると[、COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange)の既定の実装を含むいくつかの既定のハンドラー関数がコントロール クラスに自動的に追加されます。 次の例は、ActiveX コントロール ウィザードで作成されたクラスに追加されるコードを示しています。

[!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]

プロパティを永続化する場合は、プロパティ交換関数`DoPropExchange`への呼び出しを追加して変更します。 次の例は、CircleShape プロパティの既定値**が TRUE**である、カスタムブール型円シェイプ プロパティのシリアル化を示しています。

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]

次の表に、コントロールのプロパティをシリアル化するために使用できるプロパティ交換関数を示します。

|プロパティ交換機能|目的|
|---------------------------------|-------------|
|**PX_Blob( )**|型バイナリ ラージ オブジェクト (BLOB) データ プロパティをシリアル化します。|
|**PX_Bool( )**|ブール型のプロパティをシリアル化します。|
|**PX_Color( )**|型の色プロパティをシリアル化します。|
|**PX_Currency( )**|**CY**型 (通貨) プロパティをシリアル化します。|
|**PX_Double( )**|型**のダブル**プロパティをシリアル化します。|
|**PX_Font( )**|Font 型プロパティをシリアル化します。|
|**PX_Float( )**|型**float**プロパティをシリアル化します。|
|**PX_IUnknown( )**|型`LPUNKNOWN`のプロパティをシリアル化します。|
|**PX_Long( )**|型**の long**プロパティをシリアル化します。|
|**PX_Picture( )**|型のピクチャ プロパティをシリアル化します。|
|**PX_Short( )**|型**short**プロパティをシリアル化します。|
|**PX文字列( )**|型`CString`プロパティをシリアル化します。|
|**PX_ULong( )**|**型 ULONG**プロパティをシリアル化します。|
|**PX_UShort( )**|**型 USHORT**プロパティをシリアル化します。|

これらのプロパティ交換関数の詳細については、「MFC リファレンス」[の「OLE コントロールの永続化](../mfc/reference/persistence-of-ole-controls.md)」を*参照してください。*

## <a name="customizing-the-default-behavior-of-dopropexchange"></a><a name="_core_customizing_the_default_behavior_of_dopropexchange"></a>既定の動作のカスタマイズ

の既定の`DoPropertyExchange`実装 (前のトピックで示したように) は、基本クラス`COleControl`を呼び出します。 これにより、 によって`COleControl`自動的にサポートされるプロパティのセットがシリアル化されます。 この呼び出しを削除すると、オブジェクトは、重要と考えるプロパティだけをシリアル化できます。 コントロールが実装したストック プロパティの状態は、コントロール オブジェクトの呼び出しを明示的に追加しない限り、コントロール オブジェクトの保存時または読み込み時にシリアル化**PX_** されません。

## <a name="implementing-version-support"></a><a name="_core_implementing_version_support"></a>バージョン サポートの実装

バージョン サポートを使用すると、変更された ActiveX コントロールは新しい永続プロパティを追加でき、以前のバージョンのコントロールによって作成された永続的な状態を検出して読み込むことができます。 コントロールのバージョンをその永続的なデータの一部として使用できるようにするには、コントロールの`DoPropExchange`関数で[COleControl::ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion)を呼び出します。 ActiveX コントロール が ActiveX コントロール ウィザードを使用して作成された場合、この呼び出しは自動的に挿入されます。 バージョンサポートが必要ない場合は削除できます。 ただし、コントロール サイズのコストは、バージョンサポートが提供する柔軟性を高めるために非常に小さくなります (4 バイト)。

ActiveX コントロール ウィザードでコントロールが作成されなかった場合は、`COleControl::ExchangeVersion``DoPropExchange`関数の先頭に次の行を挿入して呼び出しを追加します (呼`COleControl::DoPropExchange`び出しの前)。

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

バージョン番号として任意の**DWORD**を使用できます。 ActiveX コントロール ウィザードによって生成された`_wVerMinor`プロジェクト`_wVerMajor`は、既定のプロジェクトとして使用され、既定のプロジェクトとして生成されます。 これらは、プロジェクトの ActiveX コントロール クラスの実装ファイルで定義されたグローバル定数です。 `DoPropExchange`関数の残りの部分では、[いつでも CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion)を呼び出して、保存または取得するバージョンを取得できます。

次の例では、このサンプル コントロールのバージョン 1 には"ReleaseDate" プロパティしかありません。 バージョン 2 では、"OriginalDate" プロパティが追加されます。 コントロールが古いバージョンから永続状態を読み込むように指示された場合、新しいプロパティのメンバー変数を既定値に初期化します。

[!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

既定では、コントロールは古いデータを最新の形式に変換します。 たとえば、バージョン 2 のコントロールがバージョン 1 で保存されたデータを読み込んだ場合、再び保存されるときにバージョン 2 形式が書き込まれます。 最後に読み取った形式でコントロールがデータを保存する場合**FALSE**は、 を呼び出`ExchangeVersion`すときに FALSE を 3 番目のパラメーターとして渡します。 この 3 番目のパラメーターは省略可能で、既定では**TRUE**です。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
