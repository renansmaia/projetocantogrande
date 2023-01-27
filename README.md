# projetocantogrande

[Edit on StackBlitz ⚡️](https://stackblitz.com/edit/nextjs-n872xa)

// pages/newproduct.js
import React, {useState} from 'react';

export default function NewProduct() {
  const [product, setProduct] = useState({});

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log(product);
    // Aqui você pode enviar o produto para o seu back-end para salvar no banco de dados
  }
  const handleChange = (e) => {
    setProduct({...product, [e.target.name]: e.target.value});
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Nome:
        <input type="text" name="name" onChange={handleChange}/>
      </label>
      <br/>
      <label>
        Descrição:
        <input type="text" name="description" onChange={handleChange}/>
      </label>
      <br/>
      <label>
        Preço:
        <input type="number" name="price" onChange={handleChange}/>
      </label>
      <br/>
      <input type="submit" value="Cadastrar"/>
    </form>
  )
}
