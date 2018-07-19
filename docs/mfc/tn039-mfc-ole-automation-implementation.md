---
title: 'TN039: MFC OLE オートメーションの実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9dcc179b1481c4f1f6b6a0773bba792eefffae25
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122122"
---
# <a name="tn039-mfcole-automation-implementation"></a>テクニカル ノート 39: MFC/OLE オートメーションの実装

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

## <a name="overview-of-ole-idispatch-interface"></a>OLE の IDispatch インターフェイスの概要

`IDispatch`インターフェイスは、アプリケーションは、アプリケーションの機能の使用などの他のアプリケーションなど、Visual BASIC、または他の言語をできるようにするメソッドとプロパティを公開することを意味します。 このインターフェイスの最も重要な部分は、`IDispatch::Invoke`関数。 MFC は、「ディスパッチ マップ」を使用して実装する`IDispatch::Invoke`です。 ディスパッチ マップ"shape"のレイアウトに MFC 実装の情報を提供する、 `CCmdTarget`-派生クラスを直接、オブジェクトのプロパティを操作またはメンバーを満たすために、オブジェクト内の関数を呼び出すように`IDispatch::Invoke`要求します。

ほとんどの場合、ClassWizard および MFC 連携して、アプリケーション プログラマから OLE オートメーションの詳細のほとんどを非表示にします。 プログラマは、アプリケーションに公開する実際の機能に重点を置いてし、基になるプラミングについて心配する必要はありません。

ただし、バック グラウンドで MFC の実行内容を理解する必要がある場合があります。 この注意はフレームワークを割り当てる方法を説明**DISPID**メンバー関数とプロパティにします。 MFC は、アルゴリズムの知識**DISPID**s は、アプリケーションのオブジェクトの「タイプ ライブラリ」を作成する場合など、Id がわかっている必要がある場合にのみ必要です。

## <a name="mfc-dispid-assignment"></a>MFC の DISPID の割り当て

プロパティとメソッド (オブジェクトなど、コード内のオートメーション (Visual Basic のユーザー、たとえば)、エンドユーザーの実際の名前を表示するが、オートメーションが有効にShowWindow)、実装の`IDispatch::Invoke`実際の名前を受信しません。 最適化のため、受信、 **DISPID**、これは、32 ビット"マジック"を cookie メソッドまたはプロパティへのアクセスをについて説明します。 これら**DISPID**から返される値、`IDispatch`と呼ばれる別の方法で実装`IDispatch::GetIDsOfNames`です。 オートメーション クライアント アプリケーションが呼び出す`GetIDsOfNames`アクセス、およびそれ以降の呼び出しのキャッシュが意図メンバーまたはプロパティごとに一度`IDispatch::Invoke`です。 これにより、高価な文字列の検索に一度だけ実行オブジェクトを使用して、ごとの代わりに 1 回あたり`IDispatch::Invoke`呼び出します。

MFC の決定、 **DISPID**メソッドとプロパティに基づいて 2 つの操作。

- ディスパッチ マップ (1 単位) の最上部からの距離。

- 最派生クラス (相対 0) からディスパッチ マップの距離は、

**DISPID**は 2 つの部分に分かれています。 **LOWORD**の**DISPID**最初のコンポーネントでは、ディスパッチ マップの上部からの距離が含まれています。 **ください**最派生クラスからの距離が含まれています。 例えば:

```cpp
class CDispPoint : public CCmdTarget
{
public:
    short m_x, m_y;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

class CDisp3DPoint : public CDispPoint
{
public:
    short m_z;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)
END_DISPATCH_MAP()

BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
END_DISPATCH_MAP()
```

ご覧のように、OLE オートメーション インターフェイスを公開する、2 つのクラスがあります。 これらのクラスの 1 つは、他から派生し、したがって OLE オートメーションの部分を含む、基本クラスの機能を活用して ("x"と"y"ここではプロパティ)。

MFC が生成する**DISPID**の s が CDispPoint を次のようにクラスします。

```cpp
property X    (DISPID)0x00000001
property Y    (DISPID)0x00000002
```

プロパティは、基底クラスではないため、**ください**の**DISPID**は常に 0 (CDispPoint の最も派生クラスからの距離が 0) です。

MFC が生成する**DISPID**の s が CDisp3DPoint を次のようにクラスします。

```cpp
property Z    (DISPID)0x00000001
property X    (DISPID)0x00010001
property Y    (DISPID)0x00010002
```

Z プロパティが指定された、 **DISPID**のゼロ**ください**CDisp3DPoint、プロパティを公開するクラスで定義されているためです。 X および Y プロパティが、基底クラスで定義されているため、**ください**の**DISPID**ので、これらのプロパティが定義されているクラスが 1 つの派生、最派生クラスからの距離では 1 に設定されています。

> [!NOTE]
> **LOWORD**は常に、マップ内の位置によって決定されます明示的なマップのエントリがある場合でも**DISPID** (についての情報について次のセクションを参照してください、 **_ID**バージョン、`DISP_PROPERTY`と`DISP_FUNCTION`マクロ)。

## <a name="advanced-mfc-dispatch-map-features"></a>ディスパッチ マップ機能の詳細

Visual C のこのリリースでいくつかの ClassWizard がサポートしていない追加の機能があります。 サポートされて`DISP_FUNCTION`、 `DISP_PROPERTY`、および`DISP_PROPERTY_EX`を定義するメソッド、メンバー変数のプロパティ、およびメンバー関数のプロパティを取得または設定、それぞれします。 これらの機能は、通常、ほとんどのオートメーション サーバーを作成するために必要なすべてです。

ClassWizard がサポートされているマクロは不十分である場合、次の追加のマクロを使用できます: `DISP_PROPERTY_NOTIFY`、および`DISP_PROPERTY_PARAM`です。

## <a name="disppropertynotify--macro-description"></a>DISP_PROPERTY_NOTIFY-マクロの説明

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    pszName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>パラメーター

*クラス*  
 クラスの名前です。

*pszName*  
 プロパティの外部名。

*メンバー名*  
 プロパティが格納されているメンバー変数の名前です。

*pfnAfterSet*  
 プロパティが変更されたときに呼び出すメンバー関数の名前。

*vtPropType*  
 プロパティの型を指定する値。

### <a name="remarks"></a>Remarks

このマクロは、追加の引数を受け取ってする点を除いてに、DISP_PROPERTY と似ています。 追加の引数*pfnAfterSet、* が何も返され、'void OnPropertyNotify()'、パラメーターはメンバー関数である必要があります。 呼び出される**後**メンバー変数が変更されました。

## <a name="disppropertyparam--macro-description"></a>DISP_PROPERTY_PARAM-マクロの説明

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*  
 クラスの名前です。

*pszName*  
 プロパティの外部名。

*memberGet*  
 プロパティの取得に使用するメンバー関数の名前です。

*メンバー セット*  
 このメンバー関数は、プロパティを設定するための名前です。

*vtPropType*  
 プロパティの型を指定する値。

*vtsParams*  
 領域の文字列には、各パラメーターの vts _ が区切られます。

### <a name="remarks"></a>Remarks

かなり DISP_PROPERTY_EX マクロのようにこのマクロは個別の Get および Set メンバー関数でアクセスするプロパティを定義します。 ただし、このマクロでは、プロパティのパラメーター リストを指定することができます。 これは、その他の何らかの方法でインデックスを作成またはパラメーター化されているプロパティを実装するために役立ちます。 パラメーターは常に配置されます最初に、その後にプロパティの新しい値。 例えば:

```cpp
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH, VTS_I2 VTS_I2)
```

場合は、get および set メンバー関数に相当します。

```cpp
LPDISPATCH CMyObject::GetItem(short row, short col)
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)
```

## <a name="dispxxxxid--macro-descriptions"></a>DISP_XXXX_ID-マクロの説明

```cpp
DISP_FUNCTION_ID(
    theClass,
    pszName,
    dispid,
    pfnMember,
    vtRetVal,
    vtsParams)
DISP_PROPERTY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    vtPropType)
DISP_PROPERTY_NOTIFY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    pfnAfterSet,
    vtPropType)
DISP_PROPERTY_EX_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType)
DISP_PROPERTY_PARAM_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*  
クラスの名前です。

*pszName*  
プロパティの外部名。

*dispid*  
プロパティまたはメソッドの固定 DISPID です。

*pfnGet*  
プロパティの取得に使用するメンバー関数の名前です。

*pfnSet*  
このメンバー関数は、プロパティを設定するための名前です。

*メンバー名*  
プロパティにマップするには、このメンバー変数の名前

*vtPropType*  
プロパティの型を指定する値。

*vtsParams*  
領域の文字列には、各パラメーターの vts _ が区切られます。

### <a name="remarks"></a>Remarks

これらのマクロでは、指定できる、 **DISPID** mfc によって自動的にではなくいずれかに割り当てます。 マクロ名をその ID が追加される点を除いて、同じ名前を持つこれらのマクロの詳細 (例: **DISP_PROPERTY_ID**) ID は、直後に指定されたパラメーターによって決定されます、 *pszName*パラメーター。 子を参照してください。詳細については、これらのマクロ H します。 **_ID**ディスパッチ マップの最後にエントリを配置する必要があります。 自動が影響**DISPID**以外と同じ方法で生成 **_ID**マクロのバージョンが (、 **DISPID**s は、位置によって決まります)。 例えば:

```cpp
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)
END_DISPATCH_MAP()
```

MFC は、クラス CDisp3DPoint は、Dispid を次のように生成されます。

```cpp
property X    (DISPID)0x00020003
property Y    (DISPID)0x00000002
property Z    (DISPID)0x00000001
```

固定を指定する**DISPID**有用な既存のディスパッチ インターフェイスへの旧バージョンとの互換性を維持するために、または特定のシステム定義のメソッドやプロパティを実装する (通常は、負の値によって示される**DISPID**、ように、 **DISPID_NEWENUM**コレクション)。

## <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>COleClientItem の IDispatch インターフェイスを取得します。

多くのサーバーでは、OLE サーバーの機能と共に、それらのドキュメント オブジェクト内でオートメーションをサポートします。 直接アクセスする必要は、このオートメーション インターフェイスにアクセスするために、`COleClientItem::m_lpObject`メンバー変数。 次のコードを取得、`IDispatch`インターフェイスから派生したオブジェクトを`COleClientItem`です。 見つかった場合はこの機能に必要なアプリケーションで、以下のコードを含めることができます。

```cpp
LPDISPATCH CMyClientItem::GetIDispatch()
{
    ASSERT_VALID(this);
    ASSERT(m_lpObject != NULL);

    LPUNKNOWN lpUnk = m_lpObject;

    Run();      // must be running

    LPOLELINK lpOleLink = NULL;
    if (m_lpObject->QueryInterface(IID_IOleLink,
        (LPVOID FAR*)&lpOleLink) == NOERROR)
    {
        ASSERT(lpOleLink != NULL);
        lpUnk = NULL;
        if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)
        {
            TRACE0("Warning: Link is not connected!\n");
            lpOleLink->Release();
            return NULL;
        }
        ASSERT(lpUnk != NULL);
    }

    LPDISPATCH lpDispatch = NULL;
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch) != NOERROR)
    {
        TRACE0("Warning: does not support IDispatch!\n");
        return NULL;
    }

    ASSERT(lpDispatch != NULL);
    return lpDispatch;
}
```

返されたディスパッチ インターフェイスこの関数が直接使用またはにアタッチされているし、可能性がある、`COleDispatchDriver`のタイプ セーフ アクセスします。 直接使用する場合は、呼び出すことを確認してください、`Release`メンバー使用するときに、ポインター (、`COleDispatchDriver`デストラクターは、既定で)。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)  
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)  
