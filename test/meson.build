
qxBlog_sources = [
	'qxBlog/src/author.cpp',
	'qxBlog/src/blog.cpp',
	'qxBlog/src/category.cpp',
	'qxBlog/src/comment.cpp',
	'qxBlog/src/main.cpp'
 ]

qxBlogCompositeKey_sources = [
	'qxBlogCompositeKey/src/author.cpp',
	 'qxBlogCompositeKey/src/blog.cpp',
	 'qxBlogCompositeKey/src/category.cpp',
	 'qxBlogCompositeKey/src/comment.cpp',
	 'qxBlogCompositeKey/src/main.cpp'
 ]

qxBlogCpp11_sources = [
	'qxBlogCpp11//src/author.cpp',
	'qxBlogCpp11//src/blog.cpp',
	'qxBlogCpp11//src/category.cpp',
	'qxBlogCpp11//src/comment.cpp',
	'qxBlogCpp11//src/main.cpp'
 ]

 qxBlogModelView_sources = [
	 'qxBlogModelView//src/author.cpp',
	 'qxBlogModelView//src/blog.cpp',
	 'qxBlogModelView//src/category.cpp',
	 'qxBlogModelView//src/comment.cpp',
	 'qxBlogModelView//src/main.cpp',
	 'qxBlogModelView//src/model_view_from_qxee/author.model_view.gen.cpp',
         'qxBlogModelView//src/model_view_from_qxee/blog.model_view.gen.cpp',
         'qxBlogModelView//src/model_view_from_qxee/category.model_view.gen.cpp',
         'qxBlogModelView//src/model_view_from_qxee/comment.model_view.gen.cpp'
 ]


tests = [
	[qxBlog_sources, 'qxBlog', '-D_BUILDING_QX_BLOG', []],
	[qxBlogCompositeKey_sources, 'qxBlogCompositeKey', '-D_BUILDING_QX_BLOG', []],
	[qxBlogCpp11_sources, 'qxBlogCpp11', '-D_BUILDING_QX_BLOG', []],
	[[qxBlogModelView_sources, qt.preprocess(qresources: 'qxBlogModelView/qt/rcc/qxBlogModelView.qrc',
						 moc_headers:[
						 	'qxBlogModelView/include/model_view_from_qxee/category.model_view.gen.h',
						 	'qxBlogModelView/include/model_view_from_qxee/blog.model_view.gen.h',
						 	'qxBlogModelView/include/model_view_from_qxee/comment.model_view.gen.h',
						 	'qxBlogModelView/include/model_view_from_qxee/author.model_view.gen.h'],
						moc_extra_arguments:  '-D_BUILDING_QX_BLOG'
						 	)], 'qxBlogModelView', '-D_BUILDING_QX_BLOG', [qt5gui, qt5widgets, qt5quick, qt5qml]]
]

foreach t:tests
	test_exe = executable(t[1], t[0], cpp_args : t[2], dependencies : [qxorm_dep]+t[3])
	test(t[1], test_exe)
endforeach

