### Django Indepth

Repo:  https://github.com/codingforentrepreneurs/eCommerce
File Uploads with AWS S3 + Django :   https://www.codingforentrepreneurs.com/blog/large-file-uploads-with-amazon-s3-django


![image](https://github.com/user-attachments/assets/a094c924-c2f3-48d2-82cf-82f359439df0)

```
this is used so that we dont have PRODUCT Object thing on our admin_page
    def __str__(self):
        return self.title      
```

## Django Views


### Detail View:
URL : 
    path("products/<int:pk>/",ProductDetailView.as_view(),
    path("products-fbv/<int:pk>/", product_detail_view),
    
Class Based View
```
class ProductDetailView(DetailView):
    queryset = Product.objects.all()
    template_name = "products/detail.html"

    def get_context_data(self, *args, **kwargs):
        context = super(ProductDetailView, self).get_context_data(*args, **kwargs)
        print(context)
        return context
```
Function based View
```
def product_detail_view(request, pk=None):
    instance = get_object_or_404(Product, pk=pk)
    context = {"object": instance}
    return render(request, "products/detail.html", context)
```
