---
title: 集約およびクラス ファクトリ マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_AGGREGATABLE
- atlcom/ATL::DECLARE_CLASSFACTORY
- atlcom/ATL::DECLARE_CLASSFACTORY_EX
- atlcom/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- atlcom/ATL::DECLARE_CLASSFACTORY_SINGLETON
- atlcom/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- atlcom/ATL::DECLARE_NOT_AGGREGATABLE
- atlcom/ATL::DECLARE_ONLY_AGGREGATABLE
- atlcom/ATL::DECLARE_POLY_AGGREGATABLE
- atlcom/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- atlcom/ATL::DECLARE_VIEW_STATUS
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
ms.openlocfilehash: 33f33043d1a2c824ada26399365541796178d21d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319338"
---
# <a name="aggregation-and-class-factory-macros"></a>集約およびクラス ファクトリ マクロ

これらのマクロは、集約を制御し、クラス ファクトリを宣言する方法を提供します。

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|オブジェクトを集計できることを宣言します (既定値)。|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|クラス ファクトリを、ATL の既定のクラス ファクトリである[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)として宣言します。|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|クラス ファクトリ オブジェクトをクラス ファクトリとして宣言します。|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|クラス[ファクトリとして宣言](../../atl/reference/ccomclassfactory2-class.md)します。|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|クラス ファクトリとして[宣言](../../atl/reference/ccomclassfactoryautothread-class.md)します。|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|クラス ファクトリとして[CComClassFactory シングルトン](../../atl/reference/ccomclassfactorysingleton-class.md)を宣言します。|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|仮想`GetControllingUnknown`関数を宣言します。|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|オブジェクトを集計できないことを宣言します。|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|オブジェクトを集計する必要があることを宣言します。|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|外部不明の値をチェックし、オブジェクトの集計可能または集計不可を宣言します。|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|内部オブジェクトの構築時に外部オブジェクトが削除されないように保護します。|
|[DECLARE_VIEW_STATUS](#declare_view_status)|コンテナに対する VIEWSTATUS フラグを指定します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="declare_aggregatable"></a><a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE

オブジェクトを集計できることを指定します。

```
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]集計可能として定義するクラスの名前。

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には、既定の集計モデルを指定するこのマクロが含まれています。 このデフォルトをオーバーライドするには、クラス定義で[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)または[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)マクロを指定します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_classfactory"></a><a name="declare_classfactory"></a>DECLARE_CLASSFACTORY

クラス[ファクトリとして宣言](../../atl/reference/ccomclassfactory-class.md)します。

```
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)は、このマクロを使用して、オブジェクトの既定のクラス ファクトリを宣言します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

## <a name="ccomclassfactory-class"></a><a name="ccomclassfactory_class"></a>クラスクラス

このクラスは[、IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装します。

```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>解説

`CComClassFactory`は、特定の CLSID のオブジェクトを作成するためのメソッドを含む[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装し、クラス ファクトリをメモリにロックして、新しいオブジェクトをより迅速に作成できるようにします。 `IClassFactory`は、システム レジストリに登録し、CLSID を割り当てるすべてのクラスに対して実装する必要があります。

ATL オブジェクトは、通常[、CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラス ファクトリを取得します。 このクラスには、既定[DECLARE_CLASSFACTORY](#declare_classfactory)のクラス ファクトリ`CComClassFactory`として宣言されるマクロ DECLARE_CLASSFACTORY が含まれます。 このデフォルトをオーバーライドするには、クラス定義の中で DECLARE_CLASSFACTORY*XXX*マクロのいずれかを指定します。 たとえば[、DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)マクロは、クラス ファクトリに対して指定されたクラスを使用します。

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

上記のクラス定義は、`CMyClassFactory`オブジェクトの既定のクラス ファクトリとして使用されることを指定します。 `CMyClassFactory`を派生`CComClassFactory`し、オーバーライド`CreateInstance`する必要があります。

ATL には、クラス ファクトリを宣言する他の 3 つのマクロが用意されています。

- [DECLARE_CLASSFACTORY2](#declare_classfactory2)ライセンスを使用して作成を制御する[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)を使用します。

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)複数のアパートメントにオブジェクトを作成する[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)を使用します。

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)単一の CCom オブジェクトグローバル オブジェクトを構築する[CCom](../../atl/reference/ccomobjectglobal-class.md) [クラスファクトリーシングルトン](../../atl/reference/ccomclassfactorysingleton-class.md)を使用します。

## <a name="declare_classfactory_ex"></a><a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX

クラス`cf`ファクトリであることを宣言します。

```
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>パラメーター

*Cf*<br/>
[in]クラス ファクトリ オブジェクトを実装するクラスの名前。

### <a name="remarks"></a>解説

*cf*パラメーターは[、CComClassFactory](../../atl/reference/ccomclassfactory-class.md)から派生し`CreateInstance`、メソッドをオーバーライドする必要があります。

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には[DECLARE_CLASSFACTORY](#declare_classfactory)、既定のクラス`CComClassFactory`ファクトリとして指定するDECLARE_CLASSFACTORY マクロが含まれています。 ただし、オブジェクトのクラス定義にDECLARE_CLASSFACTORY_EXマクロを含めることで、このデフォルトをオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

## <a name="declare_classfactory2"></a><a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2

クラス[ファクトリとして宣言](../../atl/reference/ccomclassfactory2-class.md)します。

```
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>パラメーター

*Lic*<br/>
[in]、 、`GetLicenseKey`および`IsLicenseValid``VerifyLicenseKey`を実装するクラス。

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には、既定のクラス ファクトリとして[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を指定する[DECLARE_CLASSFACTORY](#declare_classfactory)マクロが含まれています。 ただし、オブジェクトのクラス定義にDECLARE_CLASSFACTORY2マクロを含めることで、このデフォルトをオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

## <a name="ccomclassfactory2-class"></a><a name="ccomclassfactory2_class"></a>クラス

このクラスは[、IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)インターフェイスを実装します。

```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>パラメーター

*ライセンス*<br/>
次の静的関数を実装するクラス。

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>解説

`CComClassFactory2`[は、IClassFactory](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)の拡張機能である[IClassFactory2](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装します。 `IClassFactory2`ライセンスを使用してオブジェクトの作成を制御します。 ライセンスを受けたマシンで実行されるクラス ファクトリは、実行時のライセンス キーを提供できます。 このライセンス キーを使用すると、フル マシン ライセンスが存在しない場合に、アプリケーションでオブジェクトをインスタンス化できます。

ATL オブジェクトは、通常[、CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラス ファクトリを取得します。 このクラスには[、CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を既定のクラス ファクトリとして宣言するマクロ[DECLARE_CLASSFACTORY](#declare_classfactory)が含まれます。 を使用`CComClassFactory2`するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY2](#declare_classfactory2)マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`の`CComClassFactory2`テンプレート パラメータは、 、 、`VerifyLicenseKey``GetLicenseKey`および`IsLicenseValid`静的関数を実装する必要があります。 次に、単純なライセンス クラスの例を示します。

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2`と ライセンス`CComClassFactory2Base`の*license*両方から派生します。 `CComClassFactory2Base`、次に、から派生`IClassFactory2`し **、CComObjectRootEx\< CComグローバルスレッドモデル>。 **

## <a name="declare_classfactory_auto_thread"></a><a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD

クラス ファクトリとして[宣言](../../atl/reference/ccomclassfactoryautothread-class.md)します。

```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には、既定のクラス ファクトリとして[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を指定する[DECLARE_CLASSFACTORY](#declare_classfactory)マクロが含まれています。 ただし、オブジェクトのクラス定義にDECLARE_CLASSFACTORY_AUTO_THREADマクロを含めることで、このデフォルトをオーバーライドします。

複数のアパートメント (アウトオブプロセス サーバー) でオブジェクトを作成する場合は、クラスにDECLARE_CLASSFACTORY_AUTO_THREADを追加します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="ccomclassfactoryautothread-class"></a><a name="ccomclassfactoryautothread_class"></a>クラスクラス

このクラスは[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装し、複数のアパートメントでオブジェクトを作成できるようにします。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>解説

`CComClassFactoryAutoThread`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)に似ていますが、複数のアパートメントでオブジェクトを作成できます。 このサポートを利用するには、EXE モジュールを[派生させます](../../atl/reference/ccomautothreadmodule-class.md)。

ATL オブジェクトは、通常[、CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラス ファクトリを取得します。 このクラスには[、CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を既定のクラス ファクトリとして宣言するマクロ[DECLARE_CLASSFACTORY](#declare_classfactory)が含まれます。 を使用`CComClassFactoryAutoThread`するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="declare_classfactory_singleton"></a><a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON

クラス ファクトリとして[CComClassFactory シングルトン](../../atl/reference/ccomclassfactorysingleton-class.md)を宣言します。

```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>パラメーター

*obj*<br/>
[in]クラス オブジェクトの名前。

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には、既定のクラス ファクトリとして[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を指定する[DECLARE_CLASSFACTORY](#declare_classfactory)マクロが含まれています。 ただし、オブジェクトのクラス定義にDECLARE_CLASSFACTORY_SINGLETONマクロを含めることで、このデフォルトをオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="ccomclassfactorysingleton-class"></a><a name="ccomclassfactorysingleton_class"></a>シングルトンクラス

このクラスは[、CCom クラスファクトリー](../../atl/reference/ccomclassfactory-class.md)から派生し、単一のオブジェクトを構築するのに[は、CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を使用します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>パラメーター

*T*<br/>
あなたのクラス。

`CComClassFactorySingleton`から[派生し、](../../atl/reference/ccomclassfactory-class.md)単一のオブジェクトを構築するために[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を使用します。 メソッドを`CreateInstance`呼び出すたびに、このオブジェクトにインターフェイス ポインターを照会するだけです。

### <a name="remarks"></a>解説

ATL オブジェクトは、通常[、CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラス ファクトリを取得します。 このクラスには、既定[DECLARE_CLASSFACTORY](#declare_classfactory)のクラス ファクトリ`CComClassFactory`として宣言されるマクロ DECLARE_CLASSFACTORY が含まれます。 を使用`CComClassFactorySingleton`するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="declare_get_controlling_unknown"></a><a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN

仮想関数`GetControllingUnknown`を宣言します。

```
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>解説

このマクロは、未定義のコンパイラ エラー メッセージ`GetControllingUnknown`が表示された場合にオブジェクトに`CComAggregateCreator`追加します (たとえば、 )。

## <a name="declare_not_aggregatable"></a><a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE

オブジェクトを集計できないことを指定します。

```
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]集約可能でないクラス オブジェクトの名前。

### <a name="remarks"></a>解説

DECLARE_NOT_AGGREGATABLEオブジェクト`CreateInstance`に集計が行われると、エラー (CLASS_E_NOAGGREGATION) が返されます。

既定では[、CComCoClass](../../atl/reference/ccomcoclass-class.md)には、オブジェクトを集約できることを指定する[DECLARE_AGGREGATABLE](#declare_aggregatable)マクロが含まれています。 この既定の動作をオーバーライドするには、クラス定義にDECLARE_NOT_AGGREGATABLEを含めます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_only_aggregatable"></a><a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE

オブジェクトを集計する必要があることを指定します。

```
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]集約可能として定義するクラス オブジェクトの名前。

### <a name="remarks"></a>解説

DECLARE_ONLY_AGGREGATABLEオブジェクトを非集約オブジェクトとして実行`CoCreate`しようとすると、エラー (E_FAIL) が発生します。

既定では[、CComCoClass](../../atl/reference/ccomcoclass-class.md)には、オブジェクトを集約できることを指定する[DECLARE_AGGREGATABLE](#declare_aggregatable)マクロが含まれています。 この既定の動作をオーバーライドするには、クラス定義にDECLARE_ONLY_AGGREGATABLEを含めます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

## <a name="declare_poly_aggregatable"></a><a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE

オブジェクトの作成時に**CComPolyObject \< ** *x***>** のインスタンスが作成されることを指定します。

```
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>パラメーター

*X*<br/>
[in]集計可能または集計不可として定義するクラス オブジェクトの名前。

### <a name="remarks"></a>解説

作成中に、外部不明の値がチェックされます。 NULL の場合`IUnknown`、非集約オブジェクトに対して実装されます。 外側の不明な値が NULL`IUnknown`でない場合は、集約オブジェクトに対して実装されます。

DECLARE_POLY_AGGREGATABLEを使用する利点は、集約されたケースと`CComAggObject`非`CComObject`集約型のケースを処理するために、モジュールの両方を使用しないようにすることです。 1`CComPolyObject`つのオブジェクトが両方のケースを処理します。 つまり、モジュール内に vtable のコピーが 1 つだけ、関数のコピーが 1 つだけ存在します。 vtable が大きい場合、モジュールのサイズが大幅に減少する可能性があります。 ただし、vtable が小さい場合は`CComPolyObject`、モジュールサイズが少し大きくなる可能性があります`CComAggObject``CComObject`。

ATL コントロール ウィザードを使用してフル コントロールを作成すると、オブジェクト内でDECLARE_POLY_AGGREGATABLE マクロが自動的に宣言されます。

## <a name="declare_protect_final_construct"></a><a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT

内部集約オブジェクトが参照カウントをインクリメントし、カウントを 0 に減らす[場合は、](ccomobjectrootex-class.md#finalconstruct)オブジェクトが削除されないように保護します。

```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

## <a name="declare_view_status"></a><a name="declare_view_status"></a>DECLARE_VIEW_STATUS

このマクロを ATL ActiveX コントロールのコントロール クラスに配置して、コンテナーに対する VIEWSTATUS フラグを指定します。

```
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>パラメーター

*statusFlags*<br/>
[in]ビューステータス フラグ。 フラグのリストについては[、VIEWSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
