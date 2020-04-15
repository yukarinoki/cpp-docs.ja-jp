---
title: ランタイム オブジェクト モデル サービス
ms.date: 03/27/2019
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: f1cefdad368ebcd006dcb4ecf653247147f36d03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372939"
---
# <a name="run-time-object-model-services"></a>ランタイム オブジェクト モデル サービス

[CObject](../../mfc/reference/cobject-class.md)クラスと[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)クラスは、ランタイム クラス情報へのアクセス、シリアル化、および動的オブジェクトの作成など、いくつかのオブジェクト サービスをカプセル化します。 派生`CObject`したすべてのクラスは、この機能を継承します。

実行時クラス情報にアクセスすると、実行時にオブジェクトのクラスに関する情報を判別できます。 実行時にオブジェクトのクラスを判別する機能は、関数引数の追加の型チェックが必要な場合や、オブジェクトのクラスに基づいて特別な目的のコードを記述する必要がある場合に便利です。 ランタイム クラス情報は、C++ 言語で直接サポートされていません。

シリアル化とは、オブジェクトの内容をファイルに書き込んだり、ファイルから読み取ったりするプロセスのことです。 シリアル化を使用すると、アプリケーションの終了後もオブジェクトの内容を格納できます。 アプリケーションの再起動時に、オブジェクトをファイルから読み取ることができます。 このようなデータ オブジェクトは"永続的"と言われます。

動的オブジェクトの作成では、実行時に指定したクラスのオブジェクトを作成できます。 たとえば、ドキュメント、ビュー、およびフレーム オブジェクトは、フレームワークが動的に作成する必要があるため、動的な作成をサポートする必要があります。

次の表は、ランタイム クラス情報、シリアル化、および動的な作成をサポートする MFC マクロの一覧です。

これらのランタイム オブジェクト サービスとシリアル化の詳細については[、「CObject クラス: ランタイム クラス情報へのアクセス](../../mfc/accessing-run-time-class-information.md)」を参照してください。

### <a name="run-time-object-model-services-macros"></a>ランタイム オブジェクト モデル のサービス マクロ

|||
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|ランタイム クラス情報へのアクセスを有効にします (クラス宣言で使用する必要があります)。|
|[DECLARE_DYNCREATE](#declare_dyncreate)|実行時クラス情報への動的な作成とアクセスを有効にします (クラス宣言で使用する必要があります)。|
|[DECLARE_SERIAL](#declare_serial)|シリアル化とランタイム クラス情報へのアクセスを有効にします (クラス宣言で使用する必要があります)。|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|ランタイム クラス情報へのアクセスを有効にします (クラス実装で使用する必要があります)。|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|実行時情報への動的な作成とアクセスを有効にします (クラス実装で使用する必要があります)。|
|[IMPLEMENT_SERIAL](#implement_serial)|シリアル化とランタイム クラス情報へのアクセスを許可します (クラス実装で使用する必要があります)。|
|[RUNTIME_CLASS](#runtime_class)|指定された`CRuntimeClass`クラスに対応する構造体を返します。|

OLE では、実行時にオブジェクトを動的に作成する必要が頻繁にあります。 たとえば、OLE サーバー アプリケーションは、クライアントからの要求に応じて、OLE アイテムを動的に作成できる必要があります。 同様に、オートメーション サーバーは、オートメーション クライアントからの要求に応じてアイテムを作成できる必要があります。

このライブラリには、OLE 固有の 2 つのマクロが用意されています。

### <a name="dynamic-creation-of-ole-objects"></a>OLE オブジェクトの動的な作成

|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|コモン コントロール ライブラリが指定された API を実装しているかどうかを判断します。|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|コモン コントロール ライブラリが指定された API を実装しているかどうかを判断します。|
|[DECLARE_OLECREATE](#declare_olecreate)|OLE オートメーションを使用してオブジェクトを作成できるようにします。|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|コントロール クラス`GetUserTypeNameID`の`GetMiscStatus`メンバー関数と メンバー関数を宣言します。|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE コントロールにプロパティ ページの一覧を表示してプロパティ ページを表示することを宣言します。|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|OLE システムでオブジェクトを作成できるようにします。|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|コントロール クラス`GetUserTypeNameID`の`GetMiscStatus`および メンバー関数を実装します。|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|このマクロまたは[IMPLEMENT_OLECREATE](#implement_olecreate)は、 を使用`DECLARE_OLECREATE`するすべてのクラスの実装ファイルに含まれている必要があります。 |

## <a name="afx_comctl32_if_exists"></a><a name="afx_comctl32_if_exists"></a>AFX_COMCTL32_IF_EXISTS

コモン コントロール ライブラリが指定された API を実装しているかどうかを判断します。

### <a name="syntax"></a>構文

```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>パラメーター

*proc*<br/>
関数名を含む NULL で終わる文字列へのポインター、または関数の序数を指定します。 このパラメータが序数の場合は、下位の単語に含まれていなければなりません。上位ワードはゼロでなければなりません。 このパラメータは Unicode にする必要があります。

### <a name="remarks"></a>解説

このマクロを使用して[、(GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)を呼び出す代わりに) *proc*で指定された関数をコモン コントロール ライブラリにするかどうかを判断します。

### <a name="requirements"></a>必要条件

afxcomctl32.h, afxcomctl32.inl

## <a name="afx_comctl32_if_exists2"></a><a name="afx_comctl32_if_exists2"></a>AFX_COMCTL32_IF_EXISTS2

コモン コントロール ライブラリが指定された API を実装するかどうかを判断します (これは[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)の Unicode バージョンです)。

### <a name="syntax"></a>構文

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>パラメーター

*proc*<br/>
関数名を含む NULL で終わる文字列へのポインター、または関数の序数を指定します。 このパラメータが序数の場合は、下位の単語に含まれていなければなりません。上位ワードはゼロでなければなりません。 このパラメータは Unicode にする必要があります。

### <a name="remarks"></a>解説

このマクロを使用して[、(GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)を呼び出す代わりに) *proc*で指定された関数をコモン コントロール ライブラリにするかどうかを判断します。 このマクロは、AFX_COMCTL32_IF_EXISTSの Unicode バージョンです。

### <a name="requirements"></a>必要条件

afxcomctl32.h, afxcomctl32.inl

## <a name="declare_dynamic"></a><a name="declare_dynamic"></a>DECLARE_DYNAMIC

から`CObject`クラスを派生するときに、オブジェクトのクラスに関する実行時情報にアクセスする機能を追加します。

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

### <a name="remarks"></a>解説

DECLARE_DYNAMICマクロをクラスのヘッダー (.h) モジュールに追加し、そのモジュールをこのクラスのオブジェクトにアクセスする必要があるすべての .cpp モジュールに含めます。

DECLARE_ DYNAMIC マクロとIMPLEMENT_DYNAMIC マクロを使用する場合は、RUNTIME_CLASS マクロと関数を`CObject::IsKindOf`使用して、実行時にオブジェクトのクラスを判別できます。

DECLARE_DYNAMICがクラス宣言に含まれている場合、IMPLEMENT_DYNAMICをクラス実装に含める必要があります。

DECLARE_DYNAMIC マクロの詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

### <a name="example"></a>例

[IMPLEMENT_DYNAMIC](#implement_dynamic)の例を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="declare_dyncreate"></a><a name="declare_dyncreate"></a>DECLARE_DYNCREATE

派生クラスの`CObject`オブジェクトを実行時に動的に作成できるようにします。

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

### <a name="remarks"></a>解説

フレームワークは、この機能を使用して、新しいオブジェクトを動的に作成します。 たとえば、新しいドキュメントを開いたときに作成される新しいビューです。 フレームワークは動的に作成する必要があるため、ドキュメント、ビュー、およびフレーム の各クラスは動的な作成をサポートする必要があります。

クラスの .h モジュールにDECLARE_DYNCREATE マクロを追加し、そのモジュールをこのクラスのオブジェクトにアクセスする必要があるすべての .cpp モジュールに含めます。

DECLARE_DYNCREATEがクラス宣言に含まれている場合は、IMPLEMENT_DYNCREATEクラスの実装に含める必要があります。

DECLARE_DYNCREATE マクロの詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

> [!NOTE]
> DECLARE_DYNCREATE マクロには、DECLARE_DYNAMICのすべての機能が含まれています。

### <a name="example"></a>例

[IMPLEMENT_DYNCREATE](#implement_dyncreate)の例を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="declare_olectltype"></a><a name="declare_olectltype"></a>DECLARE_OLECTLTYPE

コントロール クラス`GetUserTypeNameID`の`GetMiscStatus`メンバー関数と メンバー関数を宣言します。

### <a name="syntax"></a>構文

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
コントロール クラスの名前。

### <a name="remarks"></a>解説

`GetUserTypeNameID`で`GetMiscStatus`宣言された純粋な仮想関数です`COleControl`。 これらの関数は純粋仮想関数であるため、コントロール クラスでオーバーライドする必要があります。 DECLARE_OLECTLTYPEに加えて、IMPLEMENT_OLECTLTYPE マクロをコントロール クラス宣言に追加する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="declare_proppageids"></a><a name="declare_proppageids"></a>DECLARE_PROPPAGEIDS

OLE コントロールにプロパティ ページの一覧を表示してプロパティ ページを表示することを宣言します。

### <a name="syntax"></a>構文

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
プロパティ ページを所有するコントロール クラスの名前。

### <a name="remarks"></a>解説

クラス宣言`DECLARE_PROPPAGEIDS`の最後にマクロを使用します。 次に、クラスのメンバー関数を定義する .cpp ファイルで、`BEGIN_PROPPAGEIDS`マクロ、各コントロールのプロパティ ページのマクロ エントリ、および`END_PROPPAGEIDS`プロパティ ページのリストの末尾を宣言するマクロを使用します。

プロパティ ページの詳細については、「 [ActiveX コントロール : プロパティ ページ](../mfc-activex-controls-property-pages.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="declare_serial"></a><a name="declare_serial"></a>DECLARE_SERIAL

シリアル化できる派生クラスに必要な`CObject`C++ ヘッダー コードを生成します。

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

### <a name="remarks"></a>解説

シリアル化とは、ファイルに対するオブジェクトの内容の書き込みまたは読み取りを行うプロセスです。

DECLARE_SERIAL マクロを .h モジュールで使用し、このクラスのオブジェクトにアクセスする必要があるすべての .cpp モジュールにそのモジュールを含めます。

DECLARE_SERIALがクラス宣言に含まれている場合、IMPLEMENT_SERIALクラスの実装に含める必要があります。

DECLARE_SERIAL マクロには、DECLARE_DYNAMICとDECLARE_DYNCREATEのすべての機能が含まれています。

AFX_API マクロを使用すると、DECLARE_SERIALマクロおよび`CArchive`IMPLEMENT_SERIALマクロを使用するクラスの抽出演算子を自動的にエクスポートできます。 クラス宣言 (.h ファイル内) を次のコードで囲みます。

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

DECLARE_SERIAL マクロの詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="implement_dynamic"></a><a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC

動的派生クラスに必要な C++`CObject`コードを生成し、実行時にクラス名と階層内の位置にアクセスします。

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*base_class_name*<br/>
基本クラスの名前。

### <a name="remarks"></a>解説

cpp モジュールで IMPLEMENT_DYNAMIC マクロを使用し、結果のオブジェクト コードを 1 回だけリンクします。

詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="implement_dyncreate"></a><a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE

DECLARE_DYNCREATE マクロ`CObject`と共に使用すると、-derived クラスのオブジェクトを実行時に動的に作成できます。

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*base_class_name*<br/>
基本クラスの実際の名前。

### <a name="remarks"></a>解説

フレームワークは、この機能を使用して、シリアル化中にディスクからオブジェクトを読み取る場合など、新しいオブジェクトを動的に作成します。 クラス実装ファイルにIMPLEMENT_DYNCREATEマクロを追加します。 詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

DECLARE_DYNCREATEマクロとIMPLEMENT_DYNCREATEマクロを使用する場合は、RUNTIME_CLASS マクロとメンバー関数を`CObject::IsKindOf`使用して、実行時にオブジェクトのクラスを決定できます。

DECLARE_DYNCREATEがクラス宣言に含まれている場合は、IMPLEMENT_DYNCREATEクラスの実装に含める必要があります。

このマクロ定義は、クラスの既定のコンストラクターを呼び出します。 非自明のコンストラクターがクラスによって明示的に実装されている場合は、既定のコンストラクターも明示的に実装する必要があります。 既定のコンストラクターをクラスの**プライベート**または**プロテクト**メンバー セクションに追加して、クラス実装の外部から呼び出されないようにすることができます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="implement_olecreate_flags"></a><a name="implement_olecreate_flags"></a>IMPLEMENT_OLECREATE_FLAGS

このマクロまたは[IMPLEMENT_OLECREATE](#implement_olecreate)は、DECLARE_OLECREATEを使用するクラスの実装ファイルに含まれている必要があります。

### <a name="syntax"></a>構文

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*external_name*<br/>
他のアプリケーションに公開されるオブジェクト名 (引用符で囲む)。

*Nflags*<br/>
次のフラグの 1 つ以上を含みます。

- `afxRegInsertable`OLE オブジェクトの [オブジェクトの挿入] ダイアログ ボックスにコントロールを表示できるようにします。
- `afxRegApartmentThreading`レジストリのスレッド モデルをスレッドモデル=アパートメントに設定します。
- `afxRegFreeThreading`レジストリのスレッド モデルをスレッド処理モデル=Free に設定します。

2 つのフラグ`afxRegApartmentThreading`を組み`afxRegFreeThreading`合わせて、ThreadingModel=Both を設定できます。 スレッド モデルの登録の詳細については、Windows SDK の[InprocServer32](/windows/win32/com/inprocserver32)を参照してください。

*l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*クラスの CLSID のコンポーネント。

### <a name="remarks"></a>解説

> [!NOTE]
> IMPLEMENT_OLECREATE_FLAGSを使用する場合は *、nFlags*パラメーターを使用して、オブジェクトがサポートするスレッド モデルを指定できます。 単一の踏み台モデルのみをサポートする場合は、IMPLEMENT_OLECREATEを使用します。

外部名は、他のアプリケーションに公開される識別子です。 クライアント アプリケーションは、外部名を使用して、オートメーション サーバーからこのクラスのオブジェクトを要求します。

OLE クラス ID は、オブジェクトの一意の 128 ビット識別子です。 構文の説明で、1 つの**長い**、2 つの**WORD**s、および 8**バイト**で構成され *、l*、 *w1*、 *w2*、b1 から*b8*が示されます。 *b1* アプリケーション ウィザードとコード ウィザードでは、必要に応じて固有の OLE クラス ID が作成されます。

### <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="implement_olectltype"></a><a name="implement_olectltype"></a>IMPLEMENT_OLECTLTYPE

コントロール クラス`GetUserTypeNameID`の`GetMiscStatus`および メンバー関数を実装します。

### <a name="syntax"></a>構文

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
コントロール クラスの名前。

*ユーザーの種類名*<br/>
コントロールの外部名を含む文字列のリソース ID。

*ドウォレミスク*<br/>
1 つ以上のフラグを含む列挙体。 この列挙の詳細については、Windows SDK[の「OLEMISC」](/windows/win32/api/oleidl/ne-oleidl-olemisc)を参照してください。

### <a name="remarks"></a>解説

IMPLEMENT_OLECTLTYPEに加えて、コントロール クラス宣言にDECLARE_OLECTLTYPE マクロを追加する必要があります。

この`GetUserTypeNameID`メンバー関数は、コントロール クラスを識別するリソース文字列を返します。 `GetMiscStatus`コントロールの OLEMISC ビットを返します。 この列挙体は、コントロールのその他の特性を説明する設定のコレクションを指定します。 OLEMISC の設定の詳細については、Windows SDK の[「OLEMISC」](/windows/win32/api/oleidl/ne-oleidl-olemisc)を参照してください。

> [!NOTE]
> ActiveX コントロール ウィザードで使用される既定の設定は、OLEMISC_ACTIVATEWHENVISIBLE、OLEMISC_SETCLIENTSITEFIRST、OLEMISC_INSIDEOUT、OLEMISC_CANTLINKINSIDE、およびOLEMISC_RECOMPOSEONRESIZEです。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="implement_serial"></a><a name="implement_serial"></a>IMPLEMENT_SERIAL

動的派生クラスに必要な C++`CObject`コードを生成し、実行時にクラス名と階層内の位置にアクセスします。

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*base_class_name*<br/>
基本クラスの名前。

*スキーマ*<br/>
旧バージョンのプログラムで作成されたデータを識別および処理するために、逆シリアル化プログラムを有効にするためにアーカイブにエンコードされる UINT の「バージョン番号」。 クラス スキーマ番号は -1 にすることはできません。

### <a name="remarks"></a>解説

cpp モジュールでIMPLEMENT_SERIAL マクロを使用します。その後、結果のオブジェクト コードを 1 回だけリンクします。

AFX_API マクロを使用すると、DECLARE_SERIALマクロおよび`CArchive`IMPLEMENT_SERIALマクロを使用するクラスの抽出演算子を自動的にエクスポートできます。 クラス宣言 (.h ファイル内) を次のコードで囲みます。

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

詳細については、 [CObject クラスのトピックを参照してください](../../mfc/using-cobject.md)。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="runtime_class"></a><a name="runtime_class"></a>RUNTIME_CLASS

C++ クラスの名前からランタイム クラス構造体を取得します。

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前 (引用符で囲まれていない)。

### <a name="remarks"></a>解説

class_name*で指定*されたクラスの[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)構造体へのポインターを返RUNTIME_CLASS。 DECLARE_DYNAMIC、DECLARE_DYNCREATE、またはDECLARE_SERIALで宣言された派生クラスだけが`CObject`、構造体へのポインターを`CRuntimeClass`返します。

詳細については、「 [CObject クラスのトピック](../../mfc/using-cobject.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afx.h

## <a name="declare_olecreate"></a><a name="declare_olecreate"></a>DECLARE_OLECREATE

OLE オートメーション`CCmdTarget`を使用して派生クラスのオブジェクトを作成できるようにします。

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

### <a name="remarks"></a>解説

このマクロを使用すると、他の OLE 対応アプリケーションでこの種類のオブジェクトを作成できます。

クラスの .h モジュールにDECLARE_OLECREATE マクロを追加し、このクラスのオブジェクトにアクセスする必要があるすべての .cpp モジュールにそのモジュールを含めます。

DECLARE_OLECREATEがクラス宣言に含まれている場合、IMPLEMENT_OLECREATEクラスの実装に含める必要があります。 DECLARE_OLECREATEを使用するクラス宣言では、DECLARE_DYNCREATEまたはDECLARE_SERIALも使用する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="implement_olecreate"></a><a name="implement_olecreate"></a>IMPLEMENT_OLECREATE

このマクロまたは[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)は、 を使用`DECLARE_OLECREATE`するすべてのクラスの実装ファイルに含まれている必要があります。

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>パラメーター

*class_name*<br/>
クラスの実際の名前。

*external_name*<br/>
他のアプリケーションに公開されるオブジェクト名 (引用符で囲む)。

*l*, *w1*, *w2*, *b1*, *b2*, *b3*, *b4*, *b5*, *b6*, *b7*, *b8*クラスの CLSID のコンポーネント。

### <a name="remarks"></a>解説

> [!NOTE]
> IMPLEMENT_OLECREATEを使用する場合、既定では、シングル スレッド モデルのみがサポートされます。 IMPLEMENT_OLECREATE_FLAGSを使用する場合は *、nFlags*パラメーターを使用して、オブジェクトがサポートするスレッド モデルを指定できます。

外部名は、他のアプリケーションに公開される識別子です。 クライアント アプリケーションは、外部名を使用して、オートメーション サーバーからこのクラスのオブジェクトを要求します。

OLE クラス ID は、オブジェクトの一意の 128 ビット識別子です。 構文の説明で、1 つの**長い**、2 つの**WORD**s、および 8**バイト**で構成され *、l*、 *w1*、 *w2*、b1 から*b8*が示されます。 *b1* アプリケーション ウィザードとコード ウィザードでは、必要に応じて固有の OLE クラス ID が作成されます。

### <a name="requirements"></a>必要条件

**ヘッダー**: afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[MFC コモン コントロール ライブラリの分離](../isolation-of-the-mfc-common-controls-library.md)<br/>
[CLSID キー](/windows/win32/com/clsid-key-hklm)
