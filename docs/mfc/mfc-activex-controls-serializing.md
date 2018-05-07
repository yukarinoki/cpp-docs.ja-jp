---
title: 'MFC ActiveX コントロール: シリアル化 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74d62411747dbe920b772b66d11cd1e2a789c5db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX コントロール : シリアル化
この記事では、ActiveX コントロールをシリアル化する方法について説明します。 シリアル化は、読み取りまたは書き込みをディスク ファイルなどの永続的なストレージ メディアへのプロセスです。 Microsoft Foundation Class (MFC) ライブラリでは、クラスでシリアル化のサポートが組み込まれて`CObject`です。 `COleControl` プロパティの交換機構を使用して ActiveX コントロールにこのサポートを拡張します。  
  
 ActiveX コントロールのシリアル化がオーバーライドすることによって実装される[使って](../mfc/reference/colecontrol-class.md#dopropexchange)です。 この関数は、読み込み中と呼ばれ、メンバー変数、またはメンバー変数が変更通知を使用して実装するすべてのプロパティを格納する、コントロール オブジェクトの保存します。  
  
 次のトピックでは、ActiveX コントロールのシリアル化に関連する主な問題を説明します。  
  
-   実装する`DoPropExchange`コントロール オブジェクトをシリアル化する関数  
  
-   [シリアル化プロセスをカスタマイズします。](#_core_customizing_the_default_behavior_of_dopropexchange)  
  
-   [バージョン サポートの実装](#_core_implementing_version_support)  
  
##  <a name="_core_implementing_the_dopropexchange_function"></a> DoPropExchange 関数を実装します。  
 コントロール プロジェクトを生成する ActiveX コントロール ウィザードを使用するといくつかの既定のハンドラー関数がの既定の実装を含む、コントロール クラスを自動的に追加[使って](../mfc/reference/colecontrol-class.md#dopropexchange)です。 次の例では、ActiveX コントロール ウィザードで作成されたクラスに追加するコードを示します。  
  
 [!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]  
  
 永続的なプロパティを作成する場合は、変更`DoPropExchange`プロパティ exchange 関数への呼び出しを追加しています。 次の例では、CircleShape プロパティが、既定の値を持つ、カスタム ブール CircleShape プロパティのシリアル化**TRUE**:  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]  
  
 コントロールのプロパティをシリアル化に使用できる有効なプロパティ exchange 関数を次の表に示します。  
  
|プロパティの exchange 関数|目的|  
|---------------------------------|-------------|  
|**PX_Blob に関するページ)**|型のバイナリ ラージ オブジェクト (BLOB) データのプロパティをシリアル化します。|  
|**PX_Bool に関するページ)**|ブール型のプロパティをシリアル化します。|  
|**PX_Color に関するページ)**|カラー型のプロパティをシリアル化します。|  
|**PX_Currency に関するページ)**|型をシリアル化**CY** (通貨) プロパティです。|  
|**PX_Double に関するページ)**|型をシリアル化**二重**プロパティです。|  
|**PX_Font に関するページ)**|フォントの種類のプロパティをシリアル化します。|  
|**PX_Float に関するページ)**|型をシリアル化**float**プロパティです。|  
|**PX_IUnknown に関するページ)**|型のプロパティをシリアル化`LPUNKNOWN`です。|  
|**PX_Long に関するページ)**|型をシリアル化**長い**プロパティです。|  
|**PX_Picture に関するページ)**|Picture プロパティの型をシリアル化します。|  
|**PX_Short に関するページ)**|型をシリアル化**短い**プロパティです。|  
|**PXstring に関するページ)**|型をシリアル化`CString`プロパティです。|  
|**PX_ULong に関するページ)**|型をシリアル化**ULONG**プロパティです。|  
|**PX_UShort に関するページ)**|型をシリアル化**USHORT**プロパティです。|  
  
 これらのプロパティ exchange 関数の詳細については、次を参照してください。[永続化の OLE コントロール](../mfc/reference/persistence-of-ole-controls.md)で、 *『 MFC リファレンス*です。  
  
##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> DoPropExchange の既定の動作をカスタマイズします。  
 既定の実装**DoPropertyExchange**基底クラスへの呼び出しは、(前のトピックを参照) として`COleControl`です。 これは、によって自動的にサポートされているプロパティのセットをシリアル化`COleControl`コントロールのカスタム プロパティのみをシリアル化するよりも多くのストレージ領域を使用します。 重要な検討するプロパティのみをシリアル化する、オブジェクトをこの呼び出しを削除できます。 保存または明示的に追加しない限り、コントロール オブジェクトを読み込むときに、コントロールが実装ストック プロパティの状態をシリアル化はできません**px _** に呼び出します。  
  
##  <a name="_core_implementing_version_support"></a> バージョン サポートの実装  
 バージョンのサポートには、改訂された ActiveX コントロールが新しいの永続的なプロパティを追加し、検出し、状態を読み込み、永続的なコントロールの以前のバージョンで作成することできますができるようにします。 コントロールのバージョンを使用できるようにする、持続データの一部として、呼び出す[COleControl::ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) 、コントロールの`DoPropExchange`関数。 ActiveX コントロールは、ActiveX コントロール ウィザードを使用して作成された場合、この呼び出しは自動的に挿入します。 バージョンのサポートが必要ない場合は、そのを削除することができます。 コントロールのサイズのコストが非常に小さな (4 バイト) のバージョンのサポートを提供する柔軟性を高めです。  
  
 コントロールが ActiveX コントロール ウィザードを使用して作成されていない場合への呼び出しを追加します。`COleControl::ExchangeVersion`の先頭に次の行を挿入することで、`DoPropExchange`関数 (呼び出しの前に`COleControl::DoPropExchange`)。  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 いずれかを使用することができます`DWORD`バージョン番号として。 ActiveX コントロール ウィザードによって生成されたプロジェクトを使用して **_wVerMinor**と **_wVerMajor**既定値として。 これらは、プロジェクトの ActiveX コントロール クラスの実装ファイルで定義されたグローバル定数です。 内の残りの部分で、`DoPropExchange`関数が呼び出すことができます[CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion)を保存または取得するバージョンを取得するには、いつでもできます。  
  
 次の例では、このサンプルのコントロールのバージョン 1 は、"ReleaseDate"プロパティのみをいます。 バージョン 2 は、"OriginalDate"プロパティを追加します。 コントロールが、古いバージョンから永続的な状態を読み込むように指示された場合は、既定値に新しいプロパティのメンバー変数を初期化します。  
  
 [!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 既定では、コントロール「に変換します」古いデータを最新の形式。 たとえば、バージョン 2 のコントロールは、バージョン 1 によって保存されたデータを読み込み場合は、出力するようにバージョン 2 の形式を再度保存するとします。 コントロール、形式最後に読み取られたデータを保存する場合は、渡す**FALSE**を呼び出すときに、3 番目のパラメーターとして`ExchangeVersion`です。 この 3 番目のパラメーターが省略可能で、 **TRUE**既定です。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

