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
ms.openlocfilehash: c06299f2fc7409476e4f5e5744ea11c962e3b173
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621198"
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX コントロール : シリアル化

この記事では、ActiveX コントロールをシリアル化する方法について説明します。 シリアル化は、ディスクファイルなどの永続的なストレージメディアからの読み取りまたは書き込みのプロセスです。 MFC (Microsoft Foundation Class) ライブラリには、クラスのシリアル化のサポートが組み込まれて `CObject` います。 `COleControl`は、プロパティ交換機構を使用して、このサポートを ActiveX コントロールに拡張します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールのシリアル化は、 [COleControl::D opropexchange](reference/colecontrol-class.md#dopropexchange)をオーバーライドすることによって実装されます。 この関数は、コントロールオブジェクトの読み込み中および保存中に呼び出され、メンバー変数またはメンバー変数と共に実装されたすべてのプロパティを変更通知と共に格納します。

次のトピックでは、ActiveX コントロールのシリアル化に関連する主な問題について説明します。

- `DoPropExchange`コントロールオブジェクトをシリアル化するための関数の実装

- [シリアル化プロセスのカスタマイズ](#_core_customizing_the_default_behavior_of_dopropexchange)

- [バージョンサポートの実装](#_core_implementing_version_support)

## <a name="implementing-the-dopropexchange-function"></a><a name="_core_implementing_the_dopropexchange_function"></a>DoPropExchange 関数の実装

ActiveX コントロールウィザードを使用してコントロールプロジェクトを生成する場合、既定の実装である[COleControl::D opropexchange](reference/colecontrol-class.md#dopropexchange)を含め、いくつかの既定のハンドラー関数がコントロールクラスに自動的に追加されます。 次の例は、ActiveX コントロールウィザードを使用して作成されたクラスに追加されたコードを示しています。

[!code-cpp[NVC_MFC_AxUI#43](codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]

プロパティを永続化する場合は、 `DoPropExchange` プロパティエクスチェンジ関数の呼び出しを追加してを変更します。 次の例では、CircleShape プロパティに既定値**TRUE**が設定されているカスタムのブール型の CircleShape プロパティのシリアル化を示します。

[!code-cpp[NVC_MFC_AxSer#1](codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#2](codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]

次の表に、コントロールのプロパティをシリアル化するために使用できる、使用可能なプロパティエクスチェンジ関数を示します。

|プロパティエクスチェンジ関数|目的|
|---------------------------------|-------------|
|**PX_Blob ()**|バイナリラージオブジェクト (BLOB) データプロパティをシリアル化します。|
|**PX_Bool ()**|型のブール型プロパティをシリアル化します。|
|**PX_Color ()**|型の色プロパティをシリアル化します。|
|**PX_Currency ()**|型**CY** (currency) プロパティをシリアル化します。|
|**PX_Double ()**|**Double**型のプロパティをシリアル化します。|
|**PX_Font ()**|フォントの種類のプロパティをシリアル化します。|
|**PX_Float ()**|**Float**型プロパティをシリアル化します。|
|**PX_IUnknown ()**|型のプロパティをシリアル化 `LPUNKNOWN` します。|
|**PX_Long ()**|**Long**型プロパティをシリアル化します。|
|**PX_Picture ()**|型 Picture プロパティをシリアル化します。|
|**PX_Short ()**|**Short**型のプロパティをシリアル化します。|
|**PXstring( )**|型プロパティをシリアル化 `CString` します。|
|**PX_ULong ()**|型**ULONG**プロパティをシリアル化します。|
|**PX_UShort ()**|型**USHORT**プロパティをシリアル化します。|

これらのプロパティエクスチェンジ関数の詳細については、「 *MFC リファレンス*の[OLE コントロールの永続](reference/persistence-of-ole-controls.md)化」を参照してください。

## <a name="customizing-the-default-behavior-of-dopropexchange"></a><a name="_core_customizing_the_default_behavior_of_dopropexchange"></a>DoPropExchange の既定の動作のカスタマイズ

(前のトピックで示されているように) の既定の実装では、 `DoPropertyExchange` 基本クラスの呼び出しが行われ `COleControl` ます。 これは、によって自動的にサポートされるプロパティのセットをシリアル化し `COleControl` ます。これは、コントロールのカスタムプロパティのみをシリアル化するよりも多くのストレージ領域を使用します。 この呼び出しを削除すると、重要と考えられるプロパティのみがオブジェクトによってシリアル化されます。 コントロールが実装されているストックプロパティの状態は、 **PX_** 呼び出しを明示的に追加しない限り、コントロールオブジェクトの保存時または読み込み時にシリアル化されません。

## <a name="implementing-version-support"></a><a name="_core_implementing_version_support"></a>バージョンサポートの実装

バージョンのサポートにより、変更された ActiveX コントロールで新しい永続的なプロパティを追加できるようになります。また、以前のバージョンのコントロールで作成された永続的な状態を検出して読み込むこともできます。 コントロールのバージョンを永続データの一部として使用できるようにするには、コントロールの関数で[COleControl:: ExchangeVersion](reference/colecontrol-class.md#exchangeversion)を呼び出し `DoPropExchange` ます。 Activex コントロールウィザードを使用して ActiveX コントロールを作成した場合、この呼び出しは自動的に挿入されます。 バージョンサポートが不要な場合は、削除できます。 ただし、バージョンサポートが提供する柔軟性を高めるために、制御サイズのコストは非常に小さい (4 バイト) です。

ActiveX コントロールウィザードを使用してコントロールを作成しなかった場合は、 `COleControl::ExchangeVersion` 関数の先頭に次の行を挿入することによって、への呼び出しを追加し `DoPropExchange` ます (への呼び出しの前 `COleControl::DoPropExchange` )。

[!code-cpp[NVC_MFC_AxSer#1](codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

任意の**DWORD**をバージョン番号として使用できます。 ActiveX コントロールウィザードによって生成されるプロジェクトは、 `_wVerMinor` 既定値としてとを使用し `_wVerMajor` ます。 これらは、プロジェクトの ActiveX コントロールクラスの実装ファイルで定義されているグローバル定数です。 関数の残りの部分では `DoPropExchange` 、 [CPropExchange:: GetVersion](reference/cpropexchange-class.md#getversion)をいつでも呼び出して、保存または取得するバージョンを取得できます。

次の例では、このサンプルコントロールのバージョン1には "ReleaseDate" プロパティのみが含まれています。 バージョン2では、"OriginalDate" プロパティが追加されます。 以前のバージョンから永続状態を読み込むようにコントロールに指示された場合は、新しいプロパティのメンバー変数を既定値に初期化します。

[!code-cpp[NVC_MFC_AxSer#4](codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

既定では、コントロールは古いデータを最新の形式に変換します。 たとえば、バージョン2のコントロールがバージョン1で保存されたデータを読み込んだ場合、バージョン2のファイルが再度保存されると、そのデータが書き込まれます。 コントロールで最後の読み取り形式のデータを保存する場合は、を呼び出すときに、3番目のパラメーターとして**FALSE**を渡し `ExchangeVersion` ます。 この3番目のパラメーターは省略可能であり、既定で**TRUE**に設定されています。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
