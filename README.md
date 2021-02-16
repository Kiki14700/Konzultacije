# Konzultacije

## Problem s @ login_required 

## Problem s ovim dijelom koda koji nije u aplikaciji
    <ul class="nav navbar-nav navbar-right">
        {% if current_user.is_authenticated %}
        <li><a href="{{url_for('logout')}}">Odjava</a></li>
        {% else %}
        <li><a href="{{url_for('login')}}">Prijava</a></li>
        {% endif %}
    </ul>
    
    @app.route('/logout')
@login_required
def logout():
    logout_user()
    flash('Odjavili ste se.', category='success')
    return redirect(url_for('index'))
