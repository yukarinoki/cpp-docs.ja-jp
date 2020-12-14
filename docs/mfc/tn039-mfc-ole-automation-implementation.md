---
description: '詳細については、「テクニカルノート 39: MFC/OLE オートメーションの実装」を参照してください。'
title: 'テクニカルノート 39: MFC-OLE オートメーションの実装'
ms.date: 06/28/2018
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
ms.openlocfilehash: caabd3719a467e534e47ca61ed8f9a9f1f0d2eb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215418"
---
# <a name="tn039-mfcole-automation-implementation"></a>テクニカル ノート 39: MFC/OLE オートメーションの実装

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

## <a name="overview-of-ole-idispatch-interface"></a>OLE IDispatch インターフェイスの概要

インターフェイスは、アプリケーションが `IDispatch` メソッドとプロパティを公開する手段であり、VISUAL BASIC などの他のアプリケーションやその他の言語がアプリケーションの機能を利用できるようにします。 このインターフェイスの最も重要な部分は、 `IDispatch::Invoke` 関数です。 MFC では、"ディスパッチマップ" を使用してを実装 `IDispatch::Invoke` します。 ディスパッチマップは、 `CCmdTarget` オブジェクトのプロパティを直接操作できるように、またはオブジェクト内でメンバー関数を呼び出して要求を満たすことができるように、派生クラスのレイアウトまたは "形状" に関する MFC 実装情報を提供し `IDispatch::Invoke` ます。

ほとんどの場合、ClassWizard と MFC は連携して、アプリケーションプログラマの OLE オートメーションの詳細をほとんど非表示にします。 プログラマは、アプリケーションで公開する実際の機能に集中するため、基になるプラミングについて心配する必要はありません。

ただし、場合によっては、MFC がバックグラウンドで実行されていることを理解する必要があります。 このメモでは、フレームワークがメンバー関数とプロパティに **DISPID** を割り当てる方法について説明します。 **DISPID** の割り当てに使用されるアルゴリズム MFC の知識は、アプリケーションのオブジェクトの "タイプライブラリ" を作成するときなど、id を知る必要がある場合にのみ必要です。

## <a name="mfc-dispid-assignment"></a>MFC の DISPID の割り当て

オートメーションのエンドユーザー (たとえば Visual Basic ユーザー) は、コード内のオートメーションが有効になっているプロパティとメソッドの実際の名前 (obj など) を参照します。ShowWindow) では、の実装は `IDispatch::Invoke` 実際の名前を受け取りません。 最適化の理由から、アクセスするメソッドまたはプロパティを記述する32ビットの "マジック cookie" である **DISPID** を受け取ります。 これらの **DISPID** 値は `IDispatch` 、と呼ばれる別のメソッドを使用して実装から返され `IDispatch::GetIDsOfNames` ます。 オートメーションクライアントアプリケーションは、 `GetIDsOfNames` アクセスするメンバーまたはプロパティごとに1回を呼び出し、後でを呼び出すためにキャッシュし `IDispatch::Invoke` ます。 これにより、コストの高い文字列参照は、呼び出しごとに1回ではなく、オブジェクトごとに1回だけ実行され `IDispatch::Invoke` ます。

MFC は、次の2つの点に基づいて、各メソッドおよびプロパティの **DISPID** を決定します。

- ディスパッチマップの上端からの距離 (1 相対)

- 最派生クラスからのディスパッチマップの距離 (0 相対)

**DISPID** は2つの部分に分かれています。 **DISPID** の **loword** には、ディスパッチマップの上部からの距離である最初のコンポーネントが含まれています。 **HIWORD** には、最派生クラスからの距離が含まれます。 次に例を示します。

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

ご覧のように、2つのクラスがあり、どちらも OLE オートメーションインターフェイスを公開しています。 これらのクラスの1つは、他のクラスから派生したものであるため、OLE オートメーションパーツ (この場合は "x" プロパティと "y" プロパティ) を含む基底クラスの機能を利用します。

MFC では、次のようにクラス CDispPoint の **DISPID** が生成されます。

```cpp
property X    (DISPID)0x00000001
property Y    (DISPID)0x00000002
```

プロパティは基底クラスに含まれていないため、 **DISPID** の **HIWORD** は常に0になります (cdisppoint の最も派生クラスからの距離はゼロです)。

MFC では、次のように CDisp3DPoint クラスの **DISPID** が生成されます。

```cpp
property Z    (DISPID)0x00000001
property X    (DISPID)0x00010001
property Y    (DISPID)0x00010002
```

Z プロパティには、プロパティ CDisp3DPoint を公開するクラスで定義されているため、 **HIWORD** が0の **DISPID** が指定されています。 X プロパティと Y プロパティは基底クラスで定義されているため、 **DISPID** の **HIWORD** は1です。これは、これらのプロパティが定義されているクラスが、最派生クラスからの1つの派生の距離であるためです。

> [!NOTE]
> 明示的な **DISPID** を持つマップ内にエントリが存在する場合でも、 **loword** は常にマップ内の位置によって決定されます (とマクロの **_ID** バージョンの詳細については、次のセクションを参照してください `DISP_PROPERTY` `DISP_FUNCTION` )。

## <a name="advanced-mfc-dispatch-map-features"></a>MFC ディスパッチマップの高度な機能

このリリースの Visual C++ では、ClassWizard がサポートしない追加機能がいくつかあります。 ClassWizard は `DISP_FUNCTION` 、 `DISP_PROPERTY` `DISP_PROPERTY_EX` メソッド、メンバー変数プロパティ、および get/set メンバー関数プロパティをそれぞれ定義する、、およびをサポートしています。 これらの機能は、通常、ほとんどのオートメーションサーバーを作成するために必要です。

次の追加マクロは、ClassWizard でサポートされているマクロが適切でない場合に使用できます。 `DISP_PROPERTY_NOTIFY` 、、および `DISP_PROPERTY_PARAM` です。

## <a name="disp_property_notify--macro-description"></a>DISP_PROPERTY_NOTIFY-マクロの説明

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    pszName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
クラスの名前

*pszName*<br/>
プロパティの外部名。

*memberName*<br/>
プロパティが格納されているメンバー変数の名前。

*pfnAfterSet*<br/>
プロパティが変更されたときに呼び出すメンバー関数の名前。

*vtPropType*<br/>
プロパティの型を指定する値。

### <a name="remarks"></a>解説

このマクロは DISP_PROPERTY とよく似ていますが、追加の引数を受け取る点が異なります。 追加の引数 *Pfnafterset* は、nothing を返すメンバー関数であり、' Void OnPropertyNotify () ' を必要としません。 メンバー変数が変更され **た後** に呼び出されます。

## <a name="disp_property_param--macro-description"></a>DISP_PROPERTY_PARAM-マクロの説明

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

*クラス*<br/>
クラスの名前

*pszName*<br/>
プロパティの外部名。

*memberGet*<br/>
プロパティを取得するために使用するメンバー関数の名前。

*セット*<br/>
プロパティの設定に使用されるメンバー関数の名前。

*vtPropType*<br/>
プロパティの型を指定する値。

*Vtsparc*<br/>
各パラメーターの VTS_ スペースで区切られた文字列。

### <a name="remarks"></a>解説

DISP_PROPERTY_EX マクロと同様に、このマクロは、個別の Get および Set メンバー関数でアクセスされるプロパティを定義します。 ただし、このマクロでは、プロパティのパラメーターリストを指定できます。 これは、他の方法でインデックスまたはパラメーター化されたプロパティを実装する場合に便利です。 パラメーターは常に最初に配置され、その後にプロパティの新しい値が続きます。 次に例を示します。

```cpp
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH, VTS_I2 VTS_I2)
```

は get および set メンバー関数に対応します。

```cpp
LPDISPATCH CMyObject::GetItem(short row, short col)
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)
```

## <a name="disp_xxxx_id--macro-descriptions"></a>DISP_XXXX_ID-マクロの説明

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

*クラス*<br/>
クラスの名前

*pszName*<br/>
プロパティの外部名。

*dispid*<br/>
プロパティまたはメソッドの固定 DISPID。

*pfnGet*<br/>
プロパティを取得するために使用するメンバー関数の名前。

*pfnSet*<br/>
プロパティの設定に使用されるメンバー関数の名前。

*memberName*<br/>
プロパティに割り当てるメンバー変数の名前

*vtPropType*<br/>
プロパティの型を指定する値。

*Vtsparc*<br/>
各パラメーターの VTS_ スペースで区切られた文字列。

### <a name="remarks"></a>解説

これらのマクロを使用すると、MFC によって自動的に割り当てられるのではなく、 **DISPID** を指定できます。 これらの高度なマクロには同じ名前が付けられます。ただし、ID がマクロ名 ( **DISP_PROPERTY_ID** など) に追加され、Id が *pszname* パラメーターの直後に指定されたパラメーターによって決定されます。 「AFXDISP.H」を参照してください。これらのマクロの詳細については、「」を参照してください。 **_ID** エントリは、ディスパッチマップの最後に配置する必要があります。 これらは、マクロの非 **_ID** バージョンと同じように、自動 **DISPID** 生成に影響します ( **dispid** は位置によって決定されます)。 次に例を示します。

```cpp
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)
END_DISPATCH_MAP()
```

MFC では、次のように CDisp3DPoint クラスの Dispid が生成されます。

```cpp
property X    (DISPID)0x00020003
property Y    (DISPID)0x00000002
property Z    (DISPID)0x00000001
```

固定 **dispid** を指定すると、以前に存在していたディスパッチインターフェイスとの下位互換性を維持したり、特定のシステム定義のメソッドまたはプロパティ (通常は **DISPID_NEWENUM** コレクションなどの負の **dispid** で示されます) を実装したりするのに役立ちます。

## <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>COleClientItem の IDispatch インターフェイスを取得する

多くのサーバーは、OLE サーバーの機能と共に、ドキュメントオブジェクト内のオートメーションをサポートします。 このオートメーションインターフェイスにアクセスするには、メンバー変数に直接アクセスする必要があり `COleClientItem::m_lpObject` ます。 次のコードは、 `IDispatch` から派生したオブジェクトのインターフェイスを取得 `COleClientItem` します。 この機能が必要な場合は、以下のコードをアプリケーションに含めることができます。

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

この関数から返されたディスパッチインターフェイスは、直接使用することも、型セーフアクセスのにアタッチすることもでき `COleDispatchDriver` ます。 直接使用する場合は、ポインターを使用するときにそのメンバーを呼び出すようにしてください `Release` ( `COleDispatchDriver` デストラクターは既定でこれを実行します)。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
