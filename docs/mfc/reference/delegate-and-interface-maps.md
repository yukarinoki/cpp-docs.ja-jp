---
title: デリゲートとインターフェイス マップ マクロ (MFC) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/30/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1e6f2e8cc501f9a466e4970d27a2e6ecd9174ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372983"
---
|||  
|-|-|  
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|デリゲートのマップを開始します。|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|コネクション マップの定義を開始します。|
|[CommandHandler デリゲート](#commandhandler)|コマンド ソースをコールバック メソッドを登録します。  |
|[END_DELEGATE_MAP](#end_delegate_map)|デリゲートのマップを終了します。|
|[END_INTERFACE_MAP](#end_interface_map)|実装ファイル内のインターフェイス マップを終了します。 |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|デリゲートのマップ内のエントリを作成します。|
|[INTERFACE_PART](#interface_part)|間で使用される、`BEGIN_INTERFACE_MAP`マクロと`END_INTERFACE_MAP`オブジェクトでサポートされる各インターフェイスに対してマクロです。|
|[MAKE_DELEGATE](#make_delegate)|マネージ コントロールをイベント ハンドラーをアタッチします。|


## <a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP
デリゲートのマップを開始します。  
   
### <a name="syntax"></a>構文    
```  
BEGIN_DELEGATE_MAP(  CLASS );  
```
### <a name="parameters"></a>パラメーター  
 `CLASS`  
 マネージ コントロールをホストするクラスです。  
   
### <a name="remarks"></a>コメント  
 このマクロは、デリゲート マップを構成するデリゲート エントリの一覧の先頭をマークします。 このマクロの使用方法の例は、次を参照してください。 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** msclr\event.h  
   
### <a name="see-also"></a>関連項目  
 [方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)
 
##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP
実装ファイルで使用する場合、コネクション マップの定義を開始します。  
   
### <a name="syntax"></a>構文    
```
BEGIN_INTERFACE_MAP( theClass, baseClass )  
```
### <a name="parameters"></a>パラメーター  
 `theClass`  
 定義するインターフェイス マップが含まれるクラス  
  
 `baseClass`  
 `theClass` の派生元のクラス。  
   
### <a name="remarks"></a>コメント  
 実装されている各インターフェイスが 1 つまたは複数`INTERFACE_PART`マクロを呼び出します。 このクラスを使用する集約ごとに、1 つある**INTERFACE_AGGREGATE**マクロ呼び出しです。  
  
 インターフェイス マップの詳細については、次を参照してください。[テクニカル ノート 38](../tn038-mfc-ole-iunknown-implementation.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
 
##  <a name="commandhandler"></a>CommandHandler デリゲート
コマンド ソースをコールバック メソッドを登録します。  
   
### <a name="syntax"></a>構文    
```  
delegate void CommandHandler(  UINT^ cmdID  );  
```
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID。  
   
### <a name="remarks"></a>コメント  
 このデリゲートは、コマンドのソースをコールバック メソッドを登録します。 コマンド ソース オブジェクトにデリゲートを追加すると、コールバック メソッドは、指定したソースからのコマンドのハンドラーになります。  
  
 詳細については、次を参照してください。[する方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)です。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  
   
### <a name="see-also"></a>関連項目  
 [方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)
 
##  <a name="commanduihandler"></a>CommandUIHandler
ユーザー インターフェイス更新コマンドのメッセージをコールバック メソッドを登録します。  
   
### <a name="syntax"></a>構文    
```  
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);  
```
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID。  
  
 `cmdUI`  
 コマンド メッセージ id。  
   
### <a name="remarks"></a>コメント  
 このデリゲートは、ユーザー インターフェイス更新コマンドのメッセージをコールバック メソッドを登録します。 `CommandUIHandler` ような[CommandHandler](#commandhandler)このデリゲートは、ユーザー インターフェイス オブジェクトの更新コマンドを使用する点を除いて。 ユーザー インターフェイス更新コマンドをマップする一対一メッセージ ハンドラーのメソッド。  
  
 Windows フォームを使用する方法については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  
   
### <a name="see-also"></a>関連項目  
 [方法: コマンドの追加にルーティングする Windows フォーム コントロール](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [CommandHandler](#commandhandler)

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP
デリゲートのマップを終了します。  
   
### <a name="syntax"></a>構文    
```  
END_DELEGATE_MAP();  
```  
   
### <a name="remarks"></a>コメント  
 このマクロは、デリゲートのマップを構成するデリゲート エントリのリストの末尾をマークします。 このマクロの使用方法の例は、次を参照してください。 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** msclr\event.h  
   
### <a name="see-also"></a>関連項目  

 [方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

 
##  <a name="end_interface_map"></a>END_INTERFACE_MAP
実装ファイル内のインターフェイス マップを終了します。  
   
### <a name="syntax"></a>構文    
```
END_INTERFACE_MAP( )    
```  
   
### <a name="remarks"></a>コメント  
 インターフェイス マップの詳細については、次を参照してください。[テクニカル ノート 38](../tn038-mfc-ole-iunknown-implementation.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [BEGIN_INTERFACE_MAP](#begin_interface_map)
 

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY
デリゲートのマップ内のエントリを作成します。  
   
### <a name="syntax"></a>構文    
```  
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);  
```
### <a name="parameters"></a>パラメーター  
 `MEMBER`  
 コントロールにアタッチされるイベント ハンドラー メソッドです。  
  
 `ARG0`  
 マネージ イベント ハンドラー メソッドの最初の引数など**オブジェクト ^** です。  
  
 `ARG1`  
 マネージ イベント ハンドラー メソッドの 2 番目の引数など**EventArgs ^** です。  
   
### <a name="remarks"></a>コメント  
 によって作成されたマネージ イベント ハンドラー デリゲートにデリゲート マップ内の各エントリが対応[MAKE_DELEGATE](#make_delegate)です。  
   
### <a name="example"></a>例  
 使用するコード例を次に示します`EVENT_DELEGATE_ENTRY`でデリゲート マップ エントリを作成する、`OnClick`イベント ハンドラーです。 また、コードの例を参照`MAKE_DELEGATE`です。 詳細については、次を参照してください。[する方法: ネイティブの C++ クラスから Windows フォーム イベントをシンク](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)です。  
  
 ```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()

```  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** msclr\event.h  
   
### <a name="see-also"></a>関連項目  
 [MAKE_DELEGATE](#make_delegate)   
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)
 

##  <a name="interface_part"></a>INTERFACE_PART
間で使用される、`BEGIN_INTERFACE_MAP`マクロと`END_INTERFACE_MAP`オブジェクトでサポートされる各インターフェイスに対してマクロです。  
   
### <a name="syntax"></a>構文    
```
INTERFACE_PART( theClass, iid, localClass)  
```
### <a name="parameters"></a>パラメーター  
 `theClass`  
 インターフェイス マップを持つクラスの名前。    
 `iid`  
 埋め込みクラスにマップするのには、IID です。    
 *マクロ*  
 ローカル クラスの名前。  
   
### <a name="remarks"></a>コメント  
 によって示されるクラスのメンバーに IID をマップすることができます`theClass`と*マクロ*です。  
  
 インターフェイス マップの詳細については、次を参照してください。[テクニカル ノート 38](../tn038-mfc-ole-iunknown-implementation.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
   
 
##  <a name="make_delegate"></a>MAKE_DELEGATE
マネージ コントロールをイベント ハンドラーをアタッチします。  
   
### <a name="syntax"></a>構文    
```  
MAKE_DELEGATE( DELEGATE,  MEMBER) ;  
```
### <a name="parameters"></a>パラメーター  
 `DELEGATE`  
 マネージ イベント ハンドラーの型を委任するよう[EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True)です。  
  
 `MEMBER`  
 コントロールにアタッチされるイベント ハンドラー メソッドの名前。  
   
### <a name="remarks"></a>コメント  
 このマクロは、型のマネージ イベント ハンドラー デリゲートを作成します。`DELEGATE`と名前の`MEMBER`します。 マネージ イベント ハンドラー デリゲートでは、マネージ イベントを処理するネイティブ クラスを使用します。  
   
### <a name="example"></a>例  
 次のコード例を呼び出す方法を示します`MAKE_DELEGATE`をアタッチする、 `OnClick` MFC コントロールにイベント ハンドラーを`MyControl`です。 MFC アプリケーションでこのマクロがどのように動作するかのより広範囲な説明については、次を参照してください。[する方法: ネイティブの C++ クラスから Windows フォーム イベントをシンク](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)です。  
  
```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```
   
### <a name="requirements"></a>要件  
 **ヘッダー:** msclr\event.h  
   
### <a name="see-also"></a>関連項目  
 [BEGIN_DELEGATE_MAP](#begin_delegate_map)   
 [END_DELEGATE_MAP](#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)
 



