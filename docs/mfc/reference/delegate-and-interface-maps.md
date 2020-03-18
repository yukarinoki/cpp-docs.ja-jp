---
title: デリゲートとインターフェイスマップマクロ (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: 8f48b916f7130551fc8d4da5bb2ebc75d8d728d5
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426745"
---
# <a name="delegate-and-interface-map-macros"></a>デリゲートとインターフェイス マップ マクロ

MFC では、デリゲートおよびインターフェイスマップに対して次のマクロがサポートされています。

|||
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|デリゲートマップを開始します。|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|は、マップマップの定義を開始します。|
|[CommandHandler デリゲート](#commandhandler)|コールバックメソッドをコマンドソースに登録します。  |
|[END_DELEGATE_MAP](#end_delegate_map)|デリゲートマップを終了します。|
|[END_INTERFACE_MAP](#end_interface_map)|実装ファイル内のインターフェイスマップを終了します。 |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|デリゲートマップにエントリを作成します。|
|[INTERFACE_PART](#interface_part)|BEGIN_INTERFACE_MAP マクロと、オブジェクトがサポートする各インターフェイスの END_INTERFACE_MAP マクロの間で使用されます。|
|[MAKE_DELEGATE](#make_delegate)|マネージコントロールにイベントハンドラーをアタッチします。|

## <a name="begin_delegate_map"></a>BEGIN_DELEGATE_MAP

デリゲートマップを開始します。

### <a name="syntax"></a>構文

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>パラメーター

*講義*<br/>
マネージコントロールがホストされるクラス。

### <a name="remarks"></a>解説

このマクロは、デリゲートマップを構成するデリゲートエントリのリストの先頭をマークします。 このマクロを使用する方法の例については、「 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** msclr\ event. h

##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP

実装ファイルで使用されている場合に、マップマップの定義を開始します。

### <a name="syntax"></a>構文

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
定義するインターフェイス マップが含まれるクラス

*baseClass*<br/>
*クラス*の派生元のクラス。

### <a name="remarks"></a>解説

実装されているインターフェイスごとに、1つ以上の INTERFACE_PART マクロの呼び出しがあります。 クラスで使用される集計ごとに、1つのマクロ呼び出し INTERFACE_AGGREGATE ます。

インターフェイスマップの詳細については、「[テクニカルノート 38](../tn038-mfc-ole-iunknown-implementation.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="commandhandler"></a>CommandHandler デリゲート

コールバックメソッドをコマンドソースに登録します。

### <a name="syntax"></a>構文

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID。

### <a name="remarks"></a>解説

このデリゲートは、コールバックメソッドをコマンドソースに登録します。 コマンドソースオブジェクトにデリゲートを追加すると、コールバックメソッドは、指定されたソースから送られるコマンドのハンドラーになります。

詳細については、「[方法: Windows フォームコントロールにコマンドルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)」を参照してください。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms (アセンブリに定義されています) (アセンブリに定義されています。

##  <a name="commanduihandler"></a>CommandUIHandler

コールバックメソッドをユーザーインターフェイス更新コマンドメッセージに登録します。

### <a name="syntax"></a>構文

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>パラメーター

*cmdID*<br/>
コマンド ID。

*cmdUI*<br/>
コマンドメッセージ ID。

### <a name="remarks"></a>解説

このデリゲートは、コールバックメソッドをユーザーインターフェイス更新コマンドメッセージに登録します。 `CommandUIHandler` は[Commandhandler](#commandhandler)に似ていますが、このデリゲートはユーザーインターフェイスオブジェクトの更新コマンドと共に使用される点が異なります。 ユーザーインターフェイスの更新コマンドは、メッセージハンドラーメソッドを使用して1対1でマップする必要があります。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms (アセンブリに定義されています) (アセンブリに定義されています。

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP

デリゲートマップを終了します。

### <a name="syntax"></a>構文

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>解説

このマクロは、デリゲートマップを構成するデリゲートエントリのリストの末尾をマークします。 このマクロを使用する方法の例については、「 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** msclr\ event. h

##  <a name="end_interface_map"></a>END_INTERFACE_MAP

実装ファイル内のインターフェイスマップを終了します。

### <a name="syntax"></a>構文

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>解説

インターフェイスマップの詳細については、「[テクニカルノート 38](../tn038-mfc-ole-iunknown-implementation.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY

デリゲートマップにエントリを作成します。

### <a name="syntax"></a>構文

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>パラメーター

*レプリカ*<br/>
コントロールにアタッチされるイベントハンドラーメソッド。

*ARG0*<br/>
マネージイベントハンドラーメソッドの1番目の引数 (`Object^`など)。

*ARG1*<br/>
マネージイベントハンドラーメソッドの2番目の引数 (`EventArgs^`など)。

### <a name="remarks"></a>解説

デリゲートマップ内の各エントリは、 [MAKE_DELEGATE](#make_delegate)によって作成されたマネージイベントハンドラーデリゲートに対応します。

### <a name="example"></a>例

次のコード例では、EVENT_DELEGATE_ENTRY を使用して、`OnClick` イベントハンドラーのデリゲートマップにエントリを作成する方法を示します。MAKE_DELEGATE のコード例も参照してください。 詳細については、「[方法: ネイティブC++クラスからイベントをシンク Windows フォーム](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)する」を参照してください。

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>必要条件

**ヘッダー:** msclr\ event. h

##  <a name="interface_part"></a>INTERFACE_PART

BEGIN_INTERFACE_MAP マクロと、オブジェクトがサポートする各インターフェイスの END_INTERFACE_MAP マクロの間で使用されます。

### <a name="syntax"></a>構文

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
インターフェイス マップを持つクラスの名前。
*iid*<br/>
埋め込みクラスにマップされる IID。
*localClass*<br/>
ローカルクラスの名前。

### <a name="remarks"></a>解説

これにより、*クラス*および*localclass*によって示されるクラスのメンバーに IID をマップできます。

インターフェイスマップの詳細については、「[テクニカルノート 38](../tn038-mfc-ole-iunknown-implementation.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="make_delegate"></a>MAKE_DELEGATE

マネージコントロールにイベントハンドラーをアタッチします。

### <a name="syntax"></a>構文

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>パラメーター

*人*<br/>
マネージイベントハンドラーデリゲートの型 ( [EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True)など)。

*レプリカ*<br/>
コントロールにアタッチされるイベントハンドラーメソッドの名前。

### <a name="remarks"></a>解説

このマクロは、name*メンバー*の*デリゲート*と型のマネージイベントハンドラーデリゲートを作成します。 マネージイベントハンドラーデリゲートを使用すると、ネイティブクラスでマネージイベントを処理できます。

### <a name="example"></a>例

次のコード例は、`MAKE_DELEGATE` を呼び出して、`OnClick` イベントハンドラーを MFC コントロール `MyControl`にアタッチする方法を示しています。 MFC アプリケーションでのこのマクロの動作の詳細については、「[方法: ネイティブC++クラスからイベントをシンク Windows フォーム](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)する」を参照してください。

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>必要条件

**ヘッダー:** msclr\ event. h

## <a name="see-also"></a>参照

[方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[マクロとグローバル](mfc-macros-and-globals.md)<br/>
