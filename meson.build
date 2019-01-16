project('QxOrm', 'cpp',default_options : ['cpp_std=c++11'])
add_project_arguments(['-D_QX_BUILDING_QX_ORM','-D_QX_MODE_RELEASE', '-D_QX_BUILDING_QX_ORM'],language: 'cpp')

gui = get_option('qt_gui')
network = get_option('qt_network')

pkg = import('pkgconfig')

moc = find_program('moc-qt5','moc')

qt = import('qt5')
qt5core = dependency('qt5', modules : 'Core')
qt5sql = dependency('qt5', modules : 'Sql')
qt5test = dependency('qt5', modules : 'Test')
qt5gui = dependency('qt5', modules : 'Gui', required: gui)


if gui ==  true
    add_project_arguments('-D_QX_ENABLE_QT_GUI',language: 'cpp')
endif

if network ==  true
    add_project_arguments('-D_QX_ENABLE_QT_NETWORK',language: 'cpp')
endif

sources = [
'src/QxMemLeak/bool_array.cpp',
'src/QxMemLeak/debug_new.cpp',
'src/QxMemLeak/mem_pool_base.cpp',
'src/QxMemLeak/static_mem_pool.cpp',
'src/QxSingleton/IxSingleton.cpp',
'src/QxSingleton/QxSingletonX.cpp',
'src/QxSingleton/QxSingletonInit.cpp',

'src/QxFactory/IxFactory.cpp',
'src/QxFactory/QxFactoryX.cpp',

'src/QxCollection/QxCollection.cpp',

'src/QxCommon/QxBool.cpp',
'src/QxCommon/QxCache.cpp',
'src/QxCommon/QxSimpleCrypt.cpp',

'src/QxConvert/QxConvert_Export.cpp',

'src/QxRegister/IxClass.cpp',
'src/QxRegister/QxClassX.cpp',

'src/QxDataMember/IxDataMember.cpp',
'src/QxDataMember/IxDataMemberX.cpp',
'src/QxDataMember/QxDataMember_QObject.cpp',

'src/QxTraits/unit_test_is_smart_ptr.cpp',
'src/QxTraits/unit_test_is_container.cpp',

'src/QxXml/QxXmlReader.cpp',
'src/QxXml/QxXmlWriter.cpp',

'src/QxDao/IxSqlQueryBuilder.cpp',
'src/QxDao/QxSqlDatabase.cpp',
'src/QxDao/IxSqlRelation.cpp',
'src/QxDao/QxSqlQuery.cpp',
'src/QxDao/QxSession.cpp',
'src/QxDao/IxDao_Helper.cpp',
'src/QxDao/IxPersistable.cpp',
'src/QxDao/QxSqlRelationLinked.cpp',
'src/QxDao/QxDaoAsync.cpp',
'src/QxDao/QxSqlRelationParams.cpp',
'src/QxDao/QxSoftDelete.cpp',
'src/QxDao/QxDateNeutral.cpp',
'src/QxDao/QxDateTimeNeutral.cpp',
'src/QxDao/QxTimeNeutral.cpp',

'src/QxDao/QxSqlElement/IxSqlElement.cpp',
'src/QxDao/QxSqlElement/QxSqlCompare.cpp',
'src/QxDao/QxSqlElement/QxSqlElementTemp.cpp',
'src/QxDao/QxSqlElement/QxSqlExpression.cpp',
'src/QxDao/QxSqlElement/QxSqlFreeText.cpp',
'src/QxDao/QxSqlElement/QxSqlIn.cpp',
'src/QxDao/QxSqlElement/QxSqlIsBetween.cpp',
'src/QxDao/QxSqlElement/QxSqlIsNull.cpp',
'src/QxDao/QxSqlElement/QxSqlLimit.cpp',
'src/QxDao/QxSqlElement/QxSqlSort.cpp',

'src/QxDao/QxSqlGenerator/IxSqlGenerator.cpp',
'src/QxDao/QxSqlGenerator/QxSqlGenerator_MySQL.cpp',
'src/QxDao/QxSqlGenerator/QxSqlGenerator_Oracle.cpp',
'src/QxDao/QxSqlGenerator/QxSqlGenerator_PostgreSQL.cpp',
'src/QxDao/QxSqlGenerator/QxSqlGenerator_SQLite.cpp',
'src/QxDao/QxSqlGenerator/QxSqlGenerator_MSSQLServer.cpp',
'src/QxDao/QxSqlGenerator/QxSqlGenerator_Standard.cpp',

'src/QxDao/QxRepository/IxRepository.cpp',
'src/QxDao/QxRepository/QxRepositoryX.cpp',

'src/QxSerialize/QxSerializeCheckInstance.cpp',

'src/QxSerialize/QxBoostSerializeHelper/IxBoostSerializeRegisterHelper.cpp',
'src/QxSerialize/QxBoostSerializeHelper/QxBoostSerializeRegisterHelperX.cpp',

'src/QxSerialize/boost/QxExportDllBoostArchive.cpp',

'src/QxSerialize/Qt/QxSerialize_QBrush.cpp',
'src/QxSerialize/Qt/QxSerialize_QByteArray.cpp',
'src/QxSerialize/Qt/QxSerialize_QColor.cpp',
'src/QxSerialize/Qt/QxSerialize_QDate.cpp',
'src/QxSerialize/Qt/QxSerialize_QDateTime.cpp',
'src/QxSerialize/Qt/QxSerialize_QFont.cpp',
'src/QxSerialize/Qt/QxSerialize_QImage.cpp',
'src/QxSerialize/Qt/QxSerialize_QMatrix.cpp',
'src/QxSerialize/Qt/QxSerialize_QObject.cpp',
'src/QxSerialize/Qt/QxSerialize_QPicture.cpp',
'src/QxSerialize/Qt/QxSerialize_QPixmap.cpp',
'src/QxSerialize/Qt/QxSerialize_QPoint.cpp',
'src/QxSerialize/Qt/QxSerialize_QRect.cpp',
'src/QxSerialize/Qt/QxSerialize_QRegExp.cpp',
'src/QxSerialize/Qt/QxSerialize_QRegion.cpp',
'src/QxSerialize/Qt/QxSerialize_QSize.cpp',
'src/QxSerialize/Qt/QxSerialize_QString.cpp',
'src/QxSerialize/Qt/QxSerialize_QStringList.cpp',
'src/QxSerialize/Qt/QxSerialize_QTime.cpp',
'src/QxSerialize/Qt/QxSerialize_QUrl.cpp',
'src/QxSerialize/Qt/QxSerialize_QUuid.cpp',
'src/QxSerialize/Qt/QxSerialize_QVariant.cpp',
'src/QxSerialize/Qt/QxSerialize_QSqlError.cpp',

'src/QxSerialize/QDataStream/QxSerializeQDataStream_primitive_type.cpp',
'src/QxSerialize/QDataStream/QxSerializeQDataStream_QObject.cpp',
'src/QxSerialize/QDataStream/QxSerializeQDataStream_QSqlError.cpp',
'src/QxSerialize/QDataStream/QxSerializeQDataStream_std_string.cpp',
'src/QxSerialize/QDataStream/QxSerializeQDataStream_qx_registered_class.cpp',

'src/QxSerialize/QJson/QxSerializeQJson_qx_registered_class.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_IxService.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_IxSqlElement.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QBrush.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QColor.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QFont.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QImage.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QMatrix.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QObject.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QPicture.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QPixmap.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QPoint.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QRect.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QRegExp.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QRegion.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QSize.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QSqlError.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QStringList.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QxInvalidValue.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QxInvalidValueX.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QxSqlQuery.cpp',
'src/QxSerialize/QJson/QxSerializeQJson_QxTransaction.cpp',

'src/QxService/IxParameter.cpp',
'src/QxService/IxService.cpp',
'src/QxService/QxConnect.cpp',
'src/QxService/QxServer.cpp',
'src/QxService/QxThread.cpp',
'src/QxService/QxThreadPool.cpp',
'src/QxService/QxTools.cpp',
'src/QxService/QxTransaction.cpp',

'src/QxValidator/IxValidator.cpp',
'src/QxValidator/IxValidatorX.cpp',
'src/QxValidator/QxInvalidValue.cpp',
'src/QxValidator/QxInvalidValueX.cpp',

'src/QxModelView/IxModel.cpp',
'src/QxModelView/QxNestedModel.cpp',
'src/QxModelView/QxModelRowCompare.cpp',

'src/main.cpp']



qxorm_inc = include_directories('include')


qxorm_preprocessed = qt.preprocess(
      moc_headers : ['include/QxModelView/IxModel.h',
                     'include/QxDao/QxDaoAsync.h']
      )

qxorm_lib = library('QxOrm',sources,qxorm_preprocessed,
	include_directories : qxorm_inc,
	dependencies : [qt5core, qt5sql],
        install: true
)

qxorm_dep = declare_dependency(link_with : qxorm_lib,
	                                include_directories : qxorm_inc,
	                                dependencies : [qt5core, qt5sql])

pkg.generate(libraries : qxorm_lib,
             subdirs : 'include',
             version : '1.4.4',
             name : 'libQxOrm',
             filebase : 'QxOrm',
             description : 'QxOrm Library.')

