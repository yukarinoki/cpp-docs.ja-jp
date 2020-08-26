---
title: ランタイム オブジェクト モデル サービス
ms.date: 03/27/2019
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: 63a82e3b05100f273be04a8718f2ecbb1510f06f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844510"
---
# <a name="run-time-object-model-services"></a>ランタイム オブジェクト モデル サービス

[CObject](../../mfc/reference/cobject-class.md)および[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)クラスは、ランタイムクラス情報へのアクセス、シリアル化、および動的オブジェクトの作成など、いくつかのオブジェクトサービスをカプセル化します。 から派生したすべてのクラスは `CObject` 、この機能を継承します。

ランタイムクラス情報へのアクセスを使用すると、実行時にオブジェクトのクラスに関する情報を確認できます。 実行時にオブジェクトのクラスを特定する機能は、関数の引数の型チェックを追加する必要がある場合や、オブジェクトのクラスに基づいて特殊な目的のコードを記述する必要がある場合に便利です。 ランタイムクラス情報は、C++ 言語で直接サポートされていません。

シリアル化とは、ファイルに対してオブジェクトの内容を書き込んだり読み取りたりする処理のことです。 アプリケーションが終了した後でも、シリアル化を使用してオブジェクトの内容を格納できます。 その後、アプリケーションの再起動時に、オブジェクトをファイルから読み取ることができます。 このようなデータオブジェクトは "永続的" と呼ばれます。

動的オブジェクトの作成では、実行時に指定したクラスのオブジェクトを作成できます。 たとえば、ドキュメント、ビュー、フレームオブジェクトは動的作成をサポートする必要があります。これは、フレームワークで動的に作成する必要があるためです。

次の表に、実行時クラス情報、シリアル化、および動的作成をサポートする MFC マクロを示します。

これらのランタイムオブジェクトサービスおよびシリアル化の詳細については、「 [CObject クラス: Run Time クラス情報へのアクセス](../../mfc/accessing-run-time-class-information.md)」を参照してください。

### <a name="run-time-object-model-services-macros"></a>ランタイムオブジェクトモデルサービスマクロ

|名前|説明|
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|ランタイムクラス情報へのアクセスを有効にします (クラス宣言で使用する必要があります)。|
|[DECLARE_DYNCREATE](#declare_dyncreate)|ランタイムクラス情報への動的な作成およびアクセスを可能にします (クラス宣言で使用する必要があります)。|
|[DECLARE_SERIAL](#declare_serial)|ランタイムクラス情報へのシリアル化とアクセスを可能にします (クラス宣言で使用する必要があります)。|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|ランタイムクラス情報へのアクセスを有効にします (クラスの実装で使用する必要があります)。|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|動的な作成とランタイム情報へのアクセスを有効にします (クラスの実装で使用する必要があります)。|
|[IMPLEMENT_SERIAL](#implement_serial)|シリアル化およびランタイムクラス情報へのアクセスを許可します (クラスの実装で使用する必要があります)。|
|[RUNTIME_CLASS](#runtime_class)|`CRuntimeClass`名前付きクラスに対応する構造体を返します。|

OLE では、実行時にオブジェクトを動的に作成する必要が頻繁に発生します。 たとえば、OLE サーバーアプリケーションは、クライアントからの要求に応答して OLE アイテムを動的に作成できる必要があります。 同様に、オートメーションサーバーは、オートメーションクライアントからの要求に応答して項目を作成できる必要があります。

Microsoft Foundation Class ライブラリには、OLE に固有の2つのマクロが用意されています。

### <a name="dynamic-creation-of-ole-objects"></a>OLE オブジェクトの動的作成

|名前|説明|
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|コモンコントロールライブラリが、指定された API を実装しているかどうかを判断します。|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|コモンコントロールライブラリが、指定された API を実装しているかどうかを判断します。|
|[DECLARE_OLECREATE](#declare_olecreate)|OLE オートメーションを使用してオブジェクトを作成できるようにします。|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|`GetUserTypeNameID` `GetMiscStatus` コントロールクラスのおよびメンバー関数を宣言します。|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE コントロールにプロパティを表示するプロパティページの一覧が用意されていることを宣言します。|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|OLE システムによってオブジェクトが作成されるようにします。|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|`GetUserTypeNameID` `GetMiscStatus` コントロールクラスのおよびメンバー関数を実装します。|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|このマクロまたは [IMPLEMENT_OLECREATE](#implement_olecreate) は、を使用するクラスの実装ファイルに記述されている必要があり `DECLARE_OLECREATE` ます。 |

## <a name="afx_comctl32_if_exists"></a><a name="afx_comctl32_if_exists"></a> AFX_COMCTL32_IF_EXISTS

コモンコントロールライブラリが、指定された API を実装しているかどうかを判断します。

### <a name="syntax"></a>構文

```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>パラメーター

*/proc*<br/>
関数名を格納している null で終わる文字列へのポインター、または関数の序数値を指定します。 このパラメーターが序数値の場合は、下位ワードである必要があります。上位ワードはゼロである必要があります。 このパラメーターは Unicode で指定する必要があります。

### <a name="remarks"></a>解説

このマクロを使用して、コモンコントロールライブラリが、 [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)を呼び出すのではなく、 *proc*によって指定された関数を使用するかどうかを判断します。

### <a name="requirements"></a>必要条件

afxcomctl32.h, afxcomctl32.h. inl

## <a name="afx_comctl32_if_exists2"></a><a name="afx_comctl32_if_exists2"></a> AFX_COMCTL32_IF_EXISTS2

コモンコントロールライブラリが、指定された API を実装するかどうかを決定します (これは [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)の Unicode バージョンです)。

### <a name="syntax"></a>構文

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>パラメーター

*/proc*<br/>
関数名を格納している null で終わる文字列へのポインター、または関数の序数値を指定します。 このパラメーターが序数値の場合は、下位ワードである必要があります。上位ワードはゼロである必要があります。 このパラメーターは Unicode で指定する必要があります。

### <a name="remarks"></a>解説

このマクロを使用して、コモンコントロールライブラリが、 [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)を呼び出すのではなく、 *proc*によって指定された関数を使用するかどうかを判断します。 このマクロは、AFX_COMCTL32_IF_EXISTS の Unicode バージョンです。

### <a name="requirements"></a>必要条件

afxcomctl32.h, afxcomctl32.h. inl

## <a name="declare_dynamic"></a><a name="declare_dynamic"></a> DECLARE_DYNAMIC

からクラスを派生させるときに、オブジェクトのクラスに関するランタイム情報にアクセスできるようにし `CObject` ます。

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

### <a name="remarks"></a>解説

クラスのヘッダー (.h) モジュールに DECLARE_DYNAMIC マクロを追加し、このクラスのオブジェクトにアクセスする必要があるすべての .cpp モジュールにそのモジュールを含めます。

説明に従って DECLARE_ 動的マクロと IMPLEMENT_DYNAMIC マクロを使用する場合は、RUNTIME_CLASS マクロと関数を使用して、 `CObject::IsKindOf` 実行時にオブジェクトのクラスを特定できます。

クラスの宣言に DECLARE_DYNAMIC が含まれている場合は、IMPLEMENT_DYNAMIC をクラスの実装に含める必要があります。

DECLARE_DYNAMIC マクロの詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

### <a name="example"></a>例

[IMPLEMENT_DYNAMIC](#implement_dynamic)の例を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="declare_dyncreate"></a><a name="declare_dyncreate"></a> DECLARE_DYNCREATE

`CObject`派生クラスのオブジェクトを実行時に動的に作成できるようにします。

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

### <a name="remarks"></a>解説

フレームワークは、この機能を使用して新しいオブジェクトを動的に作成します。 たとえば、新しいドキュメントを開いたときに作成される新しいビューです。 ドキュメント、ビュー、およびフレームクラスは、動的に作成する必要があるため、動的作成をサポートする必要があります。

クラスの .h モジュールに DECLARE_DYNCREATE マクロを追加し、このクラスのオブジェクトにアクセスする必要があるすべての .cpp モジュールにそのモジュールを含めます。

クラスの宣言に DECLARE_DYNCREATE が含まれている場合は、IMPLEMENT_DYNCREATE をクラスの実装に含める必要があります。

DECLARE_DYNCREATE マクロの詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

> [!NOTE]
> DECLARE_DYNCREATE マクロには、DECLARE_DYNAMIC のすべての機能が含まれています。

### <a name="example"></a>例

[IMPLEMENT_DYNCREATE](#implement_dyncreate)の例を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="declare_olectltype"></a><a name="declare_olectltype"></a> DECLARE_OLECTLTYPE

`GetUserTypeNameID` `GetMiscStatus` コントロールクラスのおよびメンバー関数を宣言します。

### <a name="syntax"></a>構文

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
コントロールクラスの名前。

### <a name="remarks"></a>解説

`GetUserTypeNameID` と `GetMiscStatus` は純粋仮想関数であり、で宣言されて `COleControl` います。 これらの関数は純粋仮想であるため、コントロールクラスでオーバーライドする必要があります。 DECLARE_OLECTLTYPE に加えて、コントロールクラスの宣言に IMPLEMENT_OLECTLTYPE マクロを追加する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="declare_proppageids"></a><a name="declare_proppageids"></a> DECLARE_PROPPAGEIDS

OLE コントロールにプロパティを表示するプロパティページの一覧が用意されていることを宣言します。

### <a name="syntax"></a>構文

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
プロパティページを所有するコントロールクラスの名前。

### <a name="remarks"></a>解説

`DECLARE_PROPPAGEIDS`クラス宣言の末尾にあるマクロを使用します。 次に、クラスのメンバー関数を定義する .cpp ファイルで、 `BEGIN_PROPPAGEIDS` マクロ、コントロールの各プロパティページのマクロエントリ、およびマクロを使用して、 `END_PROPPAGEIDS` プロパティページリストの末尾を宣言します。

プロパティページの詳細については、「 [ActiveX コントロール: プロパティページ](../mfc-activex-controls-property-pages.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="declare_serial"></a><a name="declare_serial"></a> DECLARE_SERIAL

シリアル化できるの派生クラスに必要な C++ ヘッダーコードを生成し `CObject` ます。

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

### <a name="remarks"></a>解説

シリアル化とは、オブジェクトの内容をファイルとの間で書き込みまたは読み取りを行うプロセスです。

.H モジュールで DECLARE_SERIAL マクロを使用し、このクラスのオブジェクトにアクセスする必要があるすべての .cpp モジュールにそのモジュールを含めます。

クラスの宣言に DECLARE_SERIAL が含まれている場合は、IMPLEMENT_SERIAL をクラスの実装に含める必要があります。

DECLARE_SERIAL マクロには、DECLARE_DYNAMIC と DECLARE_DYNCREATE のすべての機能が含まれています。

AFX_API マクロを使用する `CArchive` と、DECLARE_SERIAL と IMPLEMENT_SERIAL マクロを使用するクラスの抽出演算子を自動的にエクスポートできます。 次のコードを使用して、(.h ファイルにある) クラス宣言をかっこで囲みます。

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

DECLARE_SERIAL マクロの詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="implement_dynamic"></a><a name="implement_dynamic"></a> IMPLEMENT_DYNAMIC

`CObject`階層内のクラス名と位置への実行時アクセスを使用して、動的に派生したクラスに必要な C++ コードを生成します。

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*base_class_name*<br/>
基本クラスの名前。

### <a name="remarks"></a>解説

.Cpp モジュールで IMPLEMENT_DYNAMIC マクロを使用し、結果として得られるオブジェクトコードを1回だけリンクします。

詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="implement_dyncreate"></a><a name="implement_dyncreate"></a> IMPLEMENT_DYNCREATE

`CObject`DECLARE_DYNCREATE マクロと共に使用する場合に、派生クラスのオブジェクトを実行時に動的に作成できるようにします。

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*base_class_name*<br/>
基本クラスの実際の名前。

### <a name="remarks"></a>解説

フレームワークは、この機能を使用して、新しいオブジェクトを動的に作成します。たとえば、シリアル化中にディスクからオブジェクトを読み取る場合です。 クラス実装ファイルに IMPLEMENT_DYNCREATE マクロを追加します。 詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

DECLARE_DYNCREATE マクロと IMPLEMENT_DYNCREATE マクロを使用する場合は、RUNTIME_CLASS マクロとメンバー関数を使用し `CObject::IsKindOf` て、実行時にオブジェクトのクラスを特定できます。

クラスの宣言に DECLARE_DYNCREATE が含まれている場合は、IMPLEMENT_DYNCREATE をクラスの実装に含める必要があります。

このマクロ定義は、クラスの既定のコンストラクターを呼び出すことに注意してください。 重要でないコンストラクターがクラスによって明示的に実装されている場合は、既定のコンストラクターも明示的に実装する必要があります。 既定のコンストラクターは、クラスの **`private`** **`protected`** 実装の外部から呼び出されないように、クラスまたはメンバーのセクションに追加できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="implement_olecreate_flags"></a><a name="implement_olecreate_flags"></a> IMPLEMENT_OLECREATE_FLAGS

このマクロまたは [IMPLEMENT_OLECREATE](#implement_olecreate) は、DECLARE_OLECREATE を使用するクラスの実装ファイルに記述されている必要があります。

### <a name="syntax"></a>構文

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*external_name*<br/>
他のアプリケーションに公開されているオブジェクト名 (引用符で囲まれています)。

*nFlags*<br/>
には、次のフラグが1つ以上含まれています。

- `afxRegInsertable` OLE オブジェクトの [オブジェクトの挿入] ダイアログボックスにコントロールを表示できるようにします。
- `afxRegApartmentThreading` レジストリのスレッドモデルを ThreadingModel = アパートメントに設定します。
- `afxRegFreeThreading` レジストリのスレッドモデルを ThreadingModel = Free に設定します。

2つのフラグを組み合わせ `afxRegApartmentThreading` て、 `afxRegFreeThreading` ThreadingModel = Both を設定することができます。 スレッドモデルの登録の詳細については、Windows SDK の「 [InprocServer32](/windows/win32/com/inprocserver32) 」を参照してください。

*l*、 *w1*、 *w2*、 *b1*、 *b2*、 *b3*、 *b4*、 *b5*、 *b6*、 *b7*、 *b8* クラスの CLSID のコンポーネント。

### <a name="remarks"></a>解説

> [!NOTE]
> IMPLEMENT_OLECREATE_FLAGS を使用する場合は、 *nFlags* パラメーターを使用して、オブジェクトがサポートするスレッドモデルを指定できます。 Treading モデルのみをサポートする場合は、IMPLEMENT_OLECREATE を使用します。

外部名は、他のアプリケーションに公開される識別子です。 クライアントアプリケーションは、外部名を使用して、オートメーションサーバーからこのクラスのオブジェクトを要求します。

OLE クラス ID は、オブジェクトの一意の128ビット識別子です。 これは、 **`long`** 構文の説明で、 *l*、 *w1*、 *w2*、および*b1*によって表される、1つ、2つの**単語**、および 8**バイト***ので構成*されます。 アプリケーションウィザードとコードウィザードでは、必要に応じて一意の OLE クラス Id が作成されます。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="implement_olectltype"></a><a name="implement_olectltype"></a> IMPLEMENT_OLECTLTYPE

`GetUserTypeNameID` `GetMiscStatus` コントロールクラスのおよびメンバー関数を実装します。

### <a name="syntax"></a>構文

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
コントロールクラスの名前。

*idsUserTypeName*<br/>
コントロールの外部名を格納している文字列のリソース ID。

*dwOleMisc*<br/>
1つ以上のフラグを格納している列挙体。 この列挙体の詳細については、Windows SDK の「 [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) 」を参照してください。

### <a name="remarks"></a>解説

IMPLEMENT_OLECTLTYPE に加えて、コントロールクラスの宣言に DECLARE_OLECTLTYPE マクロを追加する必要があります。

この `GetUserTypeNameID` メンバー関数は、コントロールクラスを識別するリソース文字列を返します。 `GetMiscStatus` コントロールの OLEMISC ビットを返します。 この列挙体は、コントロールのさまざまな特性を記述する設定のコレクションを指定します。 OLEMISC 設定の詳細については、Windows SDK の「 [OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc) 」を参照してください。

> [!NOTE]
> ActiveX コントロールウィザードで使用される既定の設定は、OLEMISC_ACTIVATEWHENVISIBLE、OLEMISC_SETCLIENTSITEFIRST、OLEMISC_INSIDEOUT、OLEMISC_CANTLINKINSIDE、および OLEMISC_RECOMPOSEONRESIZE です。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="implement_serial"></a><a name="implement_serial"></a> IMPLEMENT_SERIAL

`CObject`階層内のクラス名と位置への実行時アクセスを使用して、動的に派生したクラスに必要な C++ コードを生成します。

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*base_class_name*<br/>
基本クラスの名前。

*wSchema*<br/>
逆シリアル化プログラムで、以前のバージョンのプログラムで作成されたデータを識別および処理できるように、アーカイブにエンコードされる UINT の "バージョン番号"。 クラススキーマ番号を-1 にすることはできません。

### <a name="remarks"></a>解説

.Cpp モジュールで IMPLEMENT_SERIAL マクロを使用します。次に、結果として得られるオブジェクトコードを1回だけリンクします。

AFX_API マクロを使用する `CArchive` と、DECLARE_SERIAL と IMPLEMENT_SERIAL マクロを使用するクラスの抽出演算子を自動的にエクスポートできます。 次のコードを使用して、(.h ファイルにある) クラス宣言をかっこで囲みます。

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="runtime_class"></a><a name="runtime_class"></a> RUNTIME_CLASS

C++ クラスの名前からランタイムクラス構造体を取得します。

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前 (引用符で囲まれていない)。

### <a name="remarks"></a>解説

RUNTIME_CLASS は、 *class_name*によって指定されたクラスの[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインターを返します。 `CObject`DECLARE_DYNAMIC、DECLARE_DYNCREATE、または DECLARE_SERIAL で宣言された派生クラスのみが、構造体へのポインターを返し `CRuntimeClass` ます。

詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx

## <a name="declare_olecreate"></a><a name="declare_olecreate"></a> DECLARE_OLECREATE

は `CCmdTarget` 、OLE オートメーションを使用して、派生クラスのオブジェクトを作成できるようにします。

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

### <a name="remarks"></a>解説

このマクロは、他の OLE 対応アプリケーションがこの型のオブジェクトを作成できるようにします。

クラスの .h モジュールに DECLARE_OLECREATE マクロを追加し、このクラスのオブジェクトにアクセスする必要があるすべての .cpp モジュールにそのモジュールを含めます。

クラスの宣言に DECLARE_OLECREATE が含まれている場合は、IMPLEMENT_OLECREATE をクラスの実装に含める必要があります。 DECLARE_OLECREATE を使用するクラス宣言では、DECLARE_DYNCREATE または DECLARE_SERIAL も使用する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="implement_olecreate"></a><a name="implement_olecreate"></a> IMPLEMENT_OLECREATE

このマクロまたは [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) は、を使用するクラスの実装ファイルに記述されている必要があり `DECLARE_OLECREATE` ます。

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*external_name*<br/>
他のアプリケーションに公開されているオブジェクト名 (引用符で囲まれています)。

*l*、 *w1*、 *w2*、 *b1*、 *b2*、 *b3*、 *b4*、 *b5*、 *b6*、 *b7*、 *b8* クラスの CLSID のコンポーネント。

### <a name="remarks"></a>解説

> [!NOTE]
> IMPLEMENT_OLECREATE を使用する場合、既定では、単一のスレッドモデルのみがサポートされます。 IMPLEMENT_OLECREATE_FLAGS を使用する場合は、 *nFlags* パラメーターを使用して、オブジェクトがサポートするスレッドモデルを指定できます。

外部名は、他のアプリケーションに公開される識別子です。 クライアントアプリケーションは、外部名を使用して、オートメーションサーバーからこのクラスのオブジェクトを要求します。

OLE クラス ID は、オブジェクトの一意の128ビット識別子です。 これは、 **`long`** 構文の説明で、 *l*、 *w1*、 *w2*、および*b1*によって表される、1つ、2つの**単語**、および 8**バイト***ので構成*されます。 アプリケーションウィザードとコードウィザードでは、必要に応じて一意の OLE クラス Id が作成されます。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[MFC コモンコントロールライブラリの分離](../isolation-of-the-mfc-common-controls-library.md)<br/>
[CLSID キー](/windows/win32/com/clsid-key-hklm)
