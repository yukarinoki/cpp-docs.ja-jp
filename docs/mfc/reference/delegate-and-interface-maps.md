---
title: デリゲートおよびインターフェイス マップ マクロ (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: e08597d024f5e3a74dcf47363ad3de0aa60cf6c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365834"
---
# <a name="delegate-and-interface-map-macros"></a>デリゲートとインターフェイス マップ マクロ

MFC では、デリゲートとインターフェイス マップに対して次のマクロがサポートされています。

|||
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|デリゲート マップを開始します。|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|インターフェイス マップの定義を開始します。|
|[CommandHandler デリゲート](#commandhandler)|コールバック メソッドをコマンド ソースに登録します。  |
|[END_DELEGATE_MAP](#end_delegate_map)|デリゲート マップを終了します。|
|[END_INTERFACE_MAP](#end_interface_map)|実装ファイル内のインターフェイス マップを終了します。 |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|デリゲート マップにエントリを作成します。|
|[INTERFACE_PART](#interface_part)|オブジェクトがサポートする各インターフェイスのBEGIN_INTERFACE_MAP マクロとEND_INTERFACE_MAP マクロの間で使用されます。|
|[MAKE_DELEGATE](#make_delegate)|マネージ コントロールにイベント ハンドラーをアタッチします。|

## <a name="begin_delegate_map"></a><a name="begin_delegate_map"></a>BEGIN_DELEGATE_MAP

デリゲート マップを開始します。

### <a name="syntax"></a>構文

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
マネージ コントロールがホストされるクラス。

### <a name="remarks"></a>解説

このマクロは、デリゲート マップを構成するデリゲート エントリのリストの先頭を示します。 このマクロの使用例については、「 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)」 を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** msclr\イベント.h

## <a name="begin_interface_map"></a><a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP

実装ファイルで使用される場合に、インターフェイス マップの定義を開始します。

### <a name="syntax"></a>構文

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
定義するインターフェイス マップが含まれるクラス

*Baseclass*<br/>
*クラスの*派生元のクラス。

### <a name="remarks"></a>解説

実装される各インターフェースに対して、1 つ以上の INTERFACE_PART マクロ呼び出しがあります。 クラスが使用する各集計には、マクロ呼び出しINTERFACE_AGGREGATE 1 つがあります。

インターフェイス マップの詳細については、[テクニカル ノート 38](../tn038-mfc-ole-iunknown-implementation.md)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="commandhandler-delegate"></a><a name="commandhandler"></a>コマンド ハンドラー デリゲート

コールバック メソッドをコマンド ソースに登録します。

### <a name="syntax"></a>構文

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID。

### <a name="remarks"></a>解説

このデリゲートは、コールバック メソッドをコマンド ソースに登録します。 コマンド ソース オブジェクトにデリゲートを追加すると、コールバック メソッドは、指定されたソースから取得されるコマンドのハンドラーになります。

詳細については、「[方法 : Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)」を参照してください。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

## <a name="commanduihandler"></a><a name="commanduihandler"></a>コマンド UI ハンドラー

コールバック メソッドをユーザー インターフェイス更新コマンド メッセージに登録します。

### <a name="syntax"></a>構文

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>パラメーター

*Cmdid*<br/>
コマンド ID。

*cmdUI*<br/>
コマンド メッセージ ID。

### <a name="remarks"></a>解説

このデリゲートは、コールバック メソッドをユーザー インターフェイス更新コマンド メッセージに登録します。 `CommandUIHandler`CommandHandler[CommandHandler](#commandhandler)に似ていますが、このデリゲートはユーザー インターフェイス オブジェクトの更新コマンドで使用されます。 ユーザー インターフェイスの更新コマンドは、メッセージ ハンドラー メソッドを使用して 1 対 1 でマップする必要があります。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)

## <a name="end_delegate_map"></a><a name="end_delegate_map"></a>END_DELEGATE_MAP

デリゲート マップを終了します。

### <a name="syntax"></a>構文

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>解説

このマクロは、デリゲート マップを構成するデリゲート エントリのリストの最後をマークします。 このマクロの使用例については、「 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)」 を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** msclr\イベント.h

## <a name="end_interface_map"></a><a name="end_interface_map"></a>END_INTERFACE_MAP

実装ファイル内のインターフェイス マップを終了します。

### <a name="syntax"></a>構文

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>解説

インターフェイス マップの詳細については、[テクニカル ノート 38](../tn038-mfc-ole-iunknown-implementation.md)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="event_delegate_entry"></a><a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY

デリゲート マップにエントリを作成します。

### <a name="syntax"></a>構文

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>パラメーター

*メンバー*<br/>
コントロールにアタッチするイベント ハンドラー メソッド。

*アルグ0*<br/>
マネージ`Object^`イベント ハンドラー メソッドの最初の引数 。

*ARG1*<br/>
マネージ`EventArgs^`イベント ハンドラー メソッドの 2 番目の引数 。

### <a name="remarks"></a>解説

デリゲート マップの各エントリは、 [MAKE_DELEGATE](#make_delegate)によって作成されたマネージ イベント ハンドラー デリゲートに対応します。

### <a name="example"></a>例

EVENT_DELEGATE_ENTRYを使用して、イベント ハンドラーのデリゲート マップにエントリを作成する方法を`OnClick`次のコード例に示します。MAKE_DELEGATEのコード例も参照してください。 詳細については、「[方法 : ネイティブ C++ クラスから Windows フォーム イベントをシンク](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)する 」を参照してください。

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>必要条件

**ヘッダー:** msclr\イベント.h

## <a name="interface_part"></a><a name="interface_part"></a>INTERFACE_PART

オブジェクトがサポートする各インターフェイスのBEGIN_INTERFACE_MAP マクロとEND_INTERFACE_MAP マクロの間で使用されます。

### <a name="syntax"></a>構文

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
インターフェイス マップを持つクラスの名前。
*Iid*<br/>
埋め込みクラスにマップされる IID。
*ローカルクラス*<br/>
ローカル クラスの名前。

### <a name="remarks"></a>解説

このクラスを使用すると、 Class および*localClass*で指定されたクラスのメンバーに IID*を*マップできます。

インターフェイス マップの詳細については、[テクニカル ノート 38](../tn038-mfc-ole-iunknown-implementation.md)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="make_delegate"></a><a name="make_delegate"></a>MAKE_DELEGATE

マネージ コントロールにイベント ハンドラーをアタッチします。

### <a name="syntax"></a>構文

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>パラメーター

*デリゲート*<br/>
マネージ イベント ハンドラー デリゲートの型 ( [EventHandler](/dotnet/api/system.eventhandler)など ) 。

*メンバー*<br/>
コントロールにアタッチするイベント ハンドラー メソッドの名前。

### <a name="remarks"></a>解説

このマクロは *、DELEGATE*型と*MEMBER*という名前のマネージ イベント ハンドラ デリゲートを作成します。 マネージ イベント ハンドラー デリゲートを使用すると、ネイティブ クラスでマネージ イベントを処理できます。

### <a name="example"></a>例

次のコード例は、MFC`MAKE_DELEGATE`コントロール`MyControl`にイベント`OnClick`ハンドラーをアタッチするために呼び出す方法を示しています。 MFC アプリケーションでこのマクロがどのように動作するかの詳細については、「 方法[: ネイティブ C++ クラスから Windows フォーム イベントをシンクする](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)」を参照してください。

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>必要条件

**ヘッダー:** msclr\イベント.h

## <a name="see-also"></a>関連項目

[方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[マクロとグローバル](mfc-macros-and-globals.md)<br/>
